# System map backend

[![CI](https://github.com/blw-ofag-ufag/system-map-backend/actions/workflows/ci.yml/badge.svg)](https://github.com/blw-ofag-ufag/system-map-backend/actions/workflows/ci.yml)
[![GitHub last commit](https://img.shields.io/github/last-commit/blw-ofag-ufag/system-map-backend.svg)](https://github.com/blw-ofag-ufag/system-map-backend/commits)
[![GitHub issues](https://img.shields.io/github/issues/blw-ofag-ufag/system-map-backend.svg)](https://github.com/blw-ofag-ufag/system-map-backend/issues)

This repository contains the knowledge graph of the system map of the Federal Office for Agriculture: IT systems of the Swiss agri-food sector, the data they contain, the services they provide and consume, and the organizations that operate, own or develop them.
It is built on the [semantic-web-template](https://github.com/blw-ofag-ufag/semantic-web-template) and uses its semantic web pipeline, including

1. manual data curation (data files in `src/rdf/data`),
2. OWL-based inferencing (using the ontology in `src/rdf/ontology/model.owl.ttl`),
3. SPARQL-based processing of the graph (using rules in `src/sparql/processing/...`),
4. SHACL-based graph data validation (using `src/rdf/shapes/model.shacl.ttl`),
5. a Pytest test suite,
6. uploading of the final graph to LINDAS (named graph `https://lindas.admin.ch/foag/system-map`).

The published graph is visualized by the [system map frontend](https://github.com/damian-oswald/system-map-frontend), which queries it live from LINDAS. The earlier visualizations remain in `docs/`.

> [!NOTE]
> This repository was migrated from [system-map](https://github.com/blw-ofag-ufag/system-map); its full commit history is preserved here.

## Development tools

This project uses a variety of tools to ensure robust reasoning and validation.

- [HermiT](http://www.hermit-reasoner.com/): An OWL reasoner used for logical reasoning and inferring new knowledge from the ontology and data.
- [Pytest](https://docs.pytest.org/): A testing framework used to run syntax checks and evaluate SHACL validation reports.
- [PySHACL](https://github.com/RDFLib/pySHACL): A Python engine used to validate the generated RDF graphs against SHACL shape definitions.
- [ROBOT](http://robot.obolibrary.org/): CLI tool used to merge, reason, and process RDF graphs.
- [RDFLib](https://rdflib.readthedocs.io/): A Python library used to parse, serialize, and programmatically manipulate RDF data.

## Semantic web standards

The project relies on core W3C Semantic Web standards to model, link, and validate data effectively.

- [RDF (Resource Description Framework)](https://www.w3.org/RDF/): The foundational data model used to represent information as a directed graph of triples.
- [OWL (Web Ontology Language)](https://www.w3.org/OWL/): Used to define the formal semantics, classes, and properties of the ontology.
- [SHACL (Shapes Constraint Language)](https://www.w3.org/TR/shacl/): Used to declare structural constraints and validate the integrity of the RDF data.
- [SPARQL](https://www.w3.org/TR/sparql11-overview/): The standard query language used to extract, transform, and post-process the RDF graphs.
- [Turtle](https://www.w3.org/TR/turtle/): The primary, human-readable serialization format used for all RDF files in this repository.

## Build and deployment orchestration

To streamline the workflow, this project uses `make` as its primary orchestration tool, automating everything from setup to deployment. The `Makefile` defines a single entry point to sequentially execute logical reasoning, SPARQL updates, SHACL validation and testing. `make help` lists all available targets with a short description.

1. Add variables to `.env` (for local execution)

    ``` sh
    USER=lindas-foag-system-map
    PASSWORD=********
    GRAPH=https://lindas.admin.ch/foag/system-map
    ENDPOINT=https://graphdb.lindas.admin.ch/repositories/lindas/rdf-graphs/service
    ```

2. Set up dependencies:

    ``` sh
    make setup
    ```

3. Run the build process:

    ``` sh
    make
    ```

    The default target runs `make test`, which builds the graph (reasoning, SPARQL processing and SHACL validation) and runs the Pytest suite. The processed graph is written to `build/rdf/03-processed.ttl`.

4. Upload the final data to [LINDAS](https://lindas.admin.ch/), the linked data service by the federal archives:

    **Automatic deployment**

    The deployment is automatically triggered via GitHub Actions whenever changes are pushed or merged to the `main` branch.
    To enable this, configure the environment variables listed in step 1 as **repository secrets** in your GitHub project settings (`Settings > Secrets and variables > Actions > New repository secret`).

    **Manual deployment**

    You can still upload the final data manually by running:

    ``` sh
    make publish
    ```

    By default, the publication process starts by deleting any pre-existing data in the provided named graph on LINDAS.
    You can also *just* delete any published data by running:

    ``` sh
    make delete
    ```

5. *If* you want to clean all written files:

    ``` sh
    make clean
    ```

## Subgraphs

Subgraphs of the system map show one part of the overall system without the multitude of connected nodes around it, for example [MARS III](https://blw-ofag-ufag.github.io/system-map/index.html?lang=en&subgraph=SaAA0IQkj02jgbLEb), [digiFLUX](https://blw-ofag-ufag.github.io/system-map/index.html?lang=en&subgraph=Si8UnIQkj02jgbLEb), [Acontrol](https://blw-ofag-ufag.github.io/system-map/index.html?lang=en&subgraph=Sa9PcqsvnAMuiYCjx), [AGIS](https://blw-ofag-ufag.github.io/system-map/index.html?lang=en&subgraph=SAAAX37V802JgbLEb) or [NTGS](https://blw-ofag-ufag.github.io/system-map/index.html?lang=en&subgraph=SH7U7SUsgqWmNqXA5).
An up-to-date list of all subgraphs is returned by the query `src/sparql/queries/subgraphs.rq`.

## Modelling decisions and deviations from the template

The repository follows the structure and pipeline of the semantic-web-template. These decisions are deliberate:

- **Namespace and IRIs:** The project keeps its existing namespace `https://agriculture.ld.admin.ch/system-map/` and its random identifiers (e.g. `systemmap:SvDlxaJ5YMkuZGH6k`), instead of a versioned namespace and readable IRIs. Changing them would break the frontend, saved queries and external links.
- **Hierarchy properties are not transitive:** `schema:parentOrganization`, `schema:subOrganization`, `dcterms:isPartOf` and `dcterms:hasPart` describe direct relations only, as in schema.org and Dublin Core. Indirect relations can be queried with property paths, e.g. `schema:parentOrganization+`.
- **Links to registers use `schema:sameAs`:** Organizations point to their entries in the Staatskalender and in Zefix with `schema:sameAs`, not `owl:sameAs`. `owl:sameAs` declares two IRIs to be the same individual, so the reasoner would copy all statements onto the register IRIs and create duplicate organizations.
- **No Quarto documentation:** `docs/` contains the visualizations of the system map. The documentation steps of the template are removed from the Makefile default target and from the CI; `docs/_ech.yml` only holds the name of the named graph, which the test suite reads.

## Contact

Do you have questions? Please do not hesitate to contact us at [agridata.ch@blw.admin.ch](mailto:agridata.ch@blw.admin.ch) or open an [issue in this repository](../../issues).
