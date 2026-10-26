# DigiAgriFoodCH Systemlandkarte


- [<span class="toc-section-number">1</span>
  Einleitung](#sec-introduction)
  - [<span class="toc-section-number">1.1</span>
    Anwendungsgebiet](#sec-scope)
  - [<span class="toc-section-number">1.2</span> Aufbau des
    Dokuments](#sec-structure)
- [<span class="toc-section-number">2</span> Was die Systemlandkarte
  abbildet](#sec-content)
  - [<span class="toc-section-number">2.1</span> IT-Systeme und
    Services](#sec-systems)
  - [<span class="toc-section-number">2.2</span> Datensätze und
    Datenflüsse](#sec-datasets)
  - [<span class="toc-section-number">2.3</span>
    Organisationen](#sec-organizations)
  - [<span class="toc-section-number">2.4</span>
    Rechtsgrundlagen](#sec-legal-basis)
  - [<span class="toc-section-number">2.5</span>
    Subgraphen](#sec-subgraphs)
- [<span class="toc-section-number">3</span>
  Datenmodell](#sec-data-model)
  - [<span class="toc-section-number">3.1</span>
    IT-Systeme](#sec-model-systems)
  - [<span class="toc-section-number">3.2</span>
    Datensätze](#sec-model-datasets)
  - [<span class="toc-section-number">3.3</span>
    IT-Services](#sec-model-services)
  - [<span class="toc-section-number">3.4</span>
    Organisationen](#sec-model-organizations)
  - [<span class="toc-section-number">3.5</span> Rechtsgrundlagen,
    Schlagwörter und Subgraphen](#sec-model-other)
  - [<span class="toc-section-number">3.6</span>
    Beziehungen](#sec-relations)
  - [<span class="toc-section-number">3.7</span>
    Qualitätssicherung](#sec-quality)
- [<span class="toc-section-number">4</span> Datenbezug und
  Nutzung](#sec-data-retrieval)
  - [<span class="toc-section-number">4.1</span> Bezug über
    LINDAS](#sec-lindas)
  - [<span class="toc-section-number">4.2</span>
    Visualisierung](#sec-visualisation)
  - [<span class="toc-section-number">4.3</span>
    Einschränkungen](#sec-limitations)
  - [<span class="toc-section-number">4.4</span>
    Pflege](#sec-maintenance)
- [<span class="toc-section-number">5</span> Klassen des
  Datenmodells](#sec-class-reference)
  - [<span class="toc-section-number">5.1</span>
    Namespaces](#sec-namespaces)
  - [<span class="toc-section-number">5.2</span>
    Datensatz](#sec-nodeshape-dataset)
  - [<span class="toc-section-number">5.3</span>
    Gesetzgebung](#sec-nodeshape-legislation)
  - [<span class="toc-section-number">5.4</span>
    IT-Service](#sec-nodeshape-service)
  - [<span class="toc-section-number">5.5</span>
    IT-System](#sec-nodeshape-softwareapplication)
  - [<span class="toc-section-number">5.6</span>
    Organisation](#sec-nodeshape-organization)
  - [<span class="toc-section-number">5.7</span>
    Schlagwort](#sec-nodeshape-keyword)
  - [<span class="toc-section-number">5.8</span>
    Subgraph](#sec-nodeshape-subgraph)
- [Anhang A – Referenzen](#sec-appendix-a)
- [Anhang B – Mitwirkung](#sec-appendix-b)
- [Anhang C – Abkürzungen und Glossar](#sec-appendix-c)
- [Anhang D – Änderungen gegenüber dem bisherigen
  Repository](#sec-appendix-d)
- [Anhang E – Tabellenverzeichnis](#sec-appendix-e)

# Einleitung

Im Schweizer Agrar- und Ernährungssektor betreiben Bund, Kantone und
private Organisationen eine Vielzahl von IT-Systemen: für
Direktzahlungen, für den Tierverkehr, für Kontrollen, für die
Nährstoffbilanz oder für die Betriebsführung. Viele dieser Systeme
tauschen Daten miteinander aus oder beziehen Daten voneinander. Welche
Daten in welchem System liegen, woher sie stammen und wer für ein System
zuständig ist, ist jedoch selten an einem Ort zusammenhängend
beschrieben. Das erschwert es, Datenflüsse zu verstehen,
Mehrfacherhebungen zu vermeiden und die Auswirkungen von Änderungen an
einem System abzuschätzen.

Die Systemlandkarte schliesst diese Lücke. Sie beschreibt die Systeme,
ihre Daten und ihre Beziehungen in einem gemeinsamen Wissensgraphen.

## Anwendungsgebiet

Die Systemlandkarte richtet sich an Fachpersonen, Architektinnen und
Architekten sowie Entwickelnde, die sich einen Überblick über die
IT-Landschaft des Agrar- und Ernährungssektors verschaffen oder
Datenflüsse zwischen Systemen nachvollziehen wollen. Sie umfasst
(<a href="#tbl-content" class="quarto-xref">Tabelle 1</a>):

- IT-Systeme und die Services, die sie anbieten und nutzen,
- die Datensätze, die in den Systemen enthalten sind, und deren
  Herkunft,
- die Organisationen, die Systeme betreiben, besitzen oder entwickeln,
- die Rechtsgrundlagen, auf die sich Systeme und Daten stützen, sowie
- Subgraphen, die einen thematischen Ausschnitt der Systemlandkarte
  zusammenfassen.

Nicht Gegenstand sind die Daten selbst: Die Systemlandkarte beschreibt,
*welche* Daten ein System enthält, nicht deren Inhalt. Ebenfalls nicht
enthalten sind technische Details wie Server, Netzwerke oder
Schnittstellenspezifikationen.

<div id="tbl-content">

Tabelle 1: Inhalte der Systemlandkarte (Stand Oktober 2026).

| Inhalt           | Anzahl |
|:-----------------|-------:|
| IT-Systeme       |    154 |
| Datensätze       |    127 |
| Services         |     10 |
| Organisationen   |    270 |
| Rechtsgrundlagen |     49 |
| Schlagwörter     |     20 |
| Subgraphen       |      6 |

</div>

## Aufbau des Dokuments

- <a href="#sec-content" class="quarto-xref">Kapitel 2</a> erklärt, was
  die Systemlandkarte abbildet, und zeigt die Begriffe an Beispielen.
- <a href="#sec-data-model" class="quarto-xref">Kapitel 3</a>
  beschreibt, wie diese Begriffe modelliert und miteinander verknüpft
  sind.
- <a href="#sec-data-retrieval" class="quarto-xref">Kapitel 4</a> zeigt,
  wie die Daten bezogen und gepflegt werden.
- <a href="#sec-class-reference" class="quarto-xref">Kapitel 5</a>
  dokumentiert alle Klassen und Eigenschaften.

# Was die Systemlandkarte abbildet

## IT-Systeme und Services

Ein IT-System ist eine eigenständige Anwendung, die Daten verarbeitet,
oft mit einer oder mehreren dazugehörigen Datenbanken, und von einer
Organisation betrieben wird, zum Beispiel das Agrarpolitische
Informationssystem (AGIS) des BLW. Grössere Systeme können aus
Teilsystemen bestehen. Eine eigene Gruppe bilden die
Farm-Management-Informationssysteme (FMIS), die landwirtschaftliche
Daten erfassen, verarbeiten und bereitstellen, um betriebliche
Entscheidungen zu unterstützen, etwa elektronische Feldkalender.

Ein Service ist eine technische Softwarekomponente, die über klar
definierte Schnittstellen Funktionen für andere Systeme bereitstellt. So
stellt Agate den zentralen Authentifizierungs- und
Rollenverwaltungsdienst bereit, über den sich Nutzende bei verschiedenen
Systemen anmelden, und der Beitragsberechnungsservice berechnet die
Direktzahlungen der Landwirtschaftsbetriebe.

## Datensätze und Datenflüsse

Ein Datensatz ist eine Informationseinheit, die in einem IT-System
enthalten ist. Der Begriff ist bewusst weit gefasst: Ein Datensatz kann
eine ganze Datenbank sein, eine einzelne Tabelle oder ein Dokument, zum
Beispiel die Beitragsdaten in AGIS.

Fliessen Daten von einem System in ein anderes, zeigt die
Systemlandkarte nicht nur, *dass* Daten fliessen, sondern auch *welche*
und woher sie stammen. Wie die Daten übertragen werden, spielt dabei
keine Rolle: über eine technische Schnittstelle, per E-Mail-Versand von
Tabellen oder durch manuelles Abschreiben.

Einige Datensätze werden gesondert ausgewiesen: Stammdaten wie die
BUR-Nummer oder die UID, die von vielen Systemen gemeinsam genutzt
werden, sowie Datensätze mit Personendaten oder mit besonders
schützenswerten Personendaten.

## Organisationen

Organisationen sind juristische Personen wie Behörden, Unternehmen oder
Verbände sowie deren Untereinheiten. Sie betreiben, besitzen oder
entwickeln IT-Systeme. Unterschieden werden Organisationen des Bundes,
kantonale Organisationen, darunter Landwirtschaftsämter,
Veterinärdienste und Beratungsstellen, sowie privatrechtliche
Organisationen. Organisationen können hierarchisch gegliedert sein, etwa
in Abteilungen.

## Rechtsgrundlagen

Organisationen, IT-Systeme und Datensätze können sich auf eine
Rechtsgrundlage stützen, etwa auf einen Artikel des
Landwirtschaftsgesetzes (LwG).

## Subgraphen

Ein Subgraph fasst einen thematischen Ausschnitt der Systemlandkarte
zusammen, zum Beispiel die Architektur rund um ein bestimmtes System. So
lässt sich ein Teilbereich zeigen, ohne die Vielzahl der übrigen Knoten.
<a href="#tbl-subgraphs" class="quarto-xref">Tabelle 2</a> listet die
bestehenden Subgraphen.

<div id="tbl-subgraphs">

Tabelle 2: Subgraphen der Systemlandkarte mit der Anzahl enthaltener
Knoten (Stand Oktober 2026).

| Subgraph                                        | Knoten |
|:------------------------------------------------|-------:|
| IT-Systemlandschaft im Schweizer Nutztiersektor |    139 |
| Systemlandschaft des BLW                        |     99 |
| digiFLUX Systemarchitektur                      |     50 |
| Acontrol Systemarchitektur                      |     38 |
| AGIS Systemarchitektur                          |     33 |
| MARS III Systemarchitektur                      |     27 |

</div>

# Datenmodell

Dieses Kapitel beschreibt, wie die Begriffe aus
<a href="#sec-content" class="quarto-xref">Kapitel 2</a> modelliert
sind: welche Angaben erfasst werden, welche davon Pflicht sind und wie
die Elemente miteinander verknüpft werden. Die technische Referenz mit
allen Eigenschaften ist in
<a href="#sec-class-reference" class="quarto-xref">Kapitel 5</a>
dokumentiert.

## IT-Systeme

Jedes IT-System hat einen Namen in mindestens einer der Sprachen
Deutsch, Französisch, Italienisch oder Englisch, höchstens einen pro
Sprache, sowie eine deutsche Beschreibung. Zudem muss jedes System von
einer Organisation betrieben werden. Bei 149 der 154 Systeme ist der
Betreiber direkt erfasst; die übrigen sind Teilsysteme und werden vom
Betreiber ihres übergeordneten Systems betrieben.

Optional sind eine Abkürzung, weitere Namen, eine Webseite, die
entwickelnde Organisation, die Rechtsgrundlage und Schlagwörter. Über
«ist Teil von» wird ein System einem übergeordneten System zugeordnet,
über «nutzt IT-Service» den Services, die es verwendet.

Ein Beispiel: Das Agrarpolitische Informationssystem (AGIS) wird von der
Gruppe Agrarinformationssystem AGIS des BLW betrieben, enthält fünf
Datensätze und stützt sich auf Art. 165c des Landwirtschaftsgesetzes.

## Datensätze

Jeder Datensatz liegt in einem IT-System, entweder direkt (89
Datensätze) oder als Teil eines übergeordneten Datensatzes (38). So
lässt sich eine Datenbank mit ihren Tabellen abbilden.

Datenflüsse werden über die Beziehung «wurde abgeleitet von» erfasst:
Der Datensatz im empfangenden System verweist auf den Datensatz, aus dem
er stammt. So sind etwa die Kontaktdaten der Milchproduzenten aus den
Registerdaten in AGIS abgeleitet. Die Gegenrichtung «informiert» wird
automatisch ergänzt.

13 Datensätze sind als Stammdaten gekennzeichnet; andere Datensätze
verweisen über «hat Masterdaten» darauf. 26 Datensätze sind als
Personendaten gekennzeichnet, 2 als besonders schützenswerte
Personendaten.

## IT-Services

Ein Service wird von einem IT-System bereitgestellt und von IT-Systemen
oder anderen Services genutzt. Erfasst sind zehn Services; 67 Systeme
nutzen mindestens einen davon.

## Organisationen

Jede Organisation hat einen Namen. Von den 270 Organisationen sind 70
Organisationen des Bundes, 51 kantonale Organisationen und 88
privatrechtliche Organisationen. Wo eine Organisation in einem amtlichen
Register geführt wird, verweist die Systemlandkarte auf diesen Eintrag,
statt die Angaben zu kopieren: Unternehmen werden direkt über ihren
Eintrag im Handelsregister (Zefix) identifiziert, Verwaltungseinheiten
verweisen über «Registereintrag» auf den Staatskalender.

Die Hierarchie wird über «gehört zu» abgebildet, jeweils nur die direkte
Zugehörigkeit. So gehört die Abteilung Direktzahlungen und Beiträge zu
Landwirtschaft Aargau. Ausserdem lässt sich festhalten, dass eine
Organisation Mitglied einer anderen ist, sie (teilweise) besitzt oder
Zugriff auf bestimmte Daten hat, etwa wenn eine andere Organisation als
die Betreiberin auf die Daten zugreift.

## Rechtsgrundlagen, Schlagwörter und Subgraphen

Rechtsgrundlagen werden über ihre Adresse in der Systematischen
Rechtssammlung des Bundes (Fedlex) identifiziert und tragen ihren
offiziellen Titel. Erfasst sind 49 Rechtsgrundlagen, auf die
Organisationen, IT-Systeme und Datensätze verweisen.

Schlagwörter ordnen IT-Systeme, Datensätze und Services thematisch ein.
Ein Subgraph hat einen Namen und enthält mindestens ein Element.

## Beziehungen

<a href="#tbl-relations" class="quarto-xref">Tabelle 3</a> zeigt die
Beziehungen der Systemlandkarte. Zu den meisten gibt es eine
Gegenrichtung, die bei der Verarbeitung automatisch ergänzt wird.

<div id="tbl-relations">

Tabelle 3: Die Beziehungen der Systemlandkarte mit ihrer Gegenrichtung.

| Beziehung | Gegenrichtung | Von | Zu |
|:---|:---|:---|:---|
| wird betrieben von | betreibt | IT-System | Organisation |
| entwickelt von | entwickelt | IT-System | Organisation |
| ist Teil von | hat Teil | IT-System, Datensatz, Service | dieselbe Klasse |
| nutzt IT-Service | wird verwendet von | IT-System, Service | Service |
| wird bereitgestellt von | bietet Service an | Service | IT-System |
| ist beinhaltet in | beinhaltet | Datensatz | IT-System |
| wurde abgeleitet von | informiert | Datensatz | Datensatz |
| hat Masterdaten | – | Datensatz | Datensatz |
| gehört zu | beinhaltet Suborganisation | Organisation | Organisation |
| Mitglied von | hat Mitglied | Organisation | Organisation |
| besitzt (teilweise) | ist (teilweise) in Besitz von | Organisation | Organisation |
| hat Zugriff auf | – | Organisation | IT-System, Datensatz |
| hat Rechtsgrundlage | – | Organisation, IT-System, Datensatz | Rechtsgrundlage |

</div>

## Qualitätssicherung

Bei jeder Änderung werden die Daten automatisch geprüft, bevor sie
publiziert werden. Die Regeln dafür sind in der *Shapes Constraint
Language* (SHACL) formuliert \[SHACL\]. Sie legen zum Beispiel fest,
dass jedes IT-System eine deutsche Beschreibung hat und von einer
Organisation betrieben wird, dass jeder Datensatz in einem IT-System
liegt und dass jede Beziehung auf ein Objekt der passenden Klasse zeigt.
Nur Daten, die alle Regeln erfüllen, werden publiziert.

# Datenbezug und Nutzung

## Bezug über LINDAS

Die Systemlandkarte ist auf [LINDAS](https://lindas.admin.ch/), dem
Linked Data Service der Bundesverwaltung, publiziert und kann mit SPARQL
abgefragt werden \[SPARQL\]. Das folgende Beispiel listet alle
Subgraphen mit der Anzahl ihrer Knoten:

``` rq
# SUBGRAPHS IN THE SYSTEM MAP
# Returns a table listing all subgraphs, their German name and the number of nodes in said subgraph.

PREFIX schema: <http://schema.org/>
PREFIX dcmitype: <http://purl.org/dc/dcmitype/>
PREFIX systemmap: <https://agriculture.ld.admin.ch/system-map/>

SELECT ?subgraph ?name (COUNT(?node) AS ?nodes)
FROM <https://lindas.admin.ch/foag/system-map>
WHERE {
  ?subgraph a dcmitype:Collection .
  ?subgraph schema:name ?name .
  ?subgraph systemmap:containsNodes ?node .
  FILTER(LANG(?name) = "de")
}
GROUP BY ?subgraph ?name
ORDER BY DESC(?nodes)
```

Solche Abfragen lassen sich auf <https://lindas.admin.ch/sparql/>
ausprobieren. Weitere Beispiele liegen im Repository unter
`src/sparql/queries/`.

## Visualisierung

Ein separates
[Frontend](https://github.com/damian-oswald/system-map-frontend) zeigt
die Systemlandkarte als interaktiven Graphen im Browser an und kann auf
einzelne Subgraphen gefiltert werden.

## Einschränkungen

Fehlt in der Systemlandkarte eine Angabe, heisst das nicht, dass es sie
nicht gibt, sondern nur, dass sie nicht erfasst ist. Ist ein Datensatz
nicht als Personendaten gekennzeichnet, kann er dennoch Personendaten
enthalten.

## Pflege

Die Systemlandkarte wird auf GitHub gepflegt. Fehler oder fehlende
Einträge können als
[Issue](https://github.com/blw-ofag-ufag/system-map-backend/issues)
gemeldet werden. Die Inhalte stehen unter der Lizenz [CC BY
4.0](https://creativecommons.org/licenses/by/4.0/) und dürfen unter
Nennung der Quelle frei verwendet werden.

# Klassen des Datenmodells

Dieses Kapitel dokumentiert alle Klassen der Systemlandkarte mit ihren
Eigenschaften. Es wird automatisch aus den SHACL-Shapes erzeugt, mit
denen die Daten geprüft werden, und ist deshalb immer auf dem Stand der
Regeln.

## Namespaces

<a href="#tbl-namespaces" class="quarto-xref">Tabelle 4</a> listet die
Präfixe und die zugehörigen Namespaces, die in diesem Kapitel verwendet
werden.

<div id="tbl-namespaces">

Tabelle 4: In DigiAgriFoodCH Systemlandkarte verwendete Namespaces.

| Präfix       | Namespace                                            |
|:-------------|:-----------------------------------------------------|
| `dcat:`      | <http://www.w3.org/ns/dcat#>                         |
| `dcmitype:`  | <http://purl.org/dc/dcmitype/>                       |
| `dcterms:`   | <http://purl.org/dc/terms/>                          |
| `prov:`      | <http://www.w3.org/ns/prov#>                         |
| `rdf:`       | <http://www.w3.org/1999/02/22-rdf-syntax-ns#>        |
| `rdfs:`      | <http://www.w3.org/2000/01/rdf-schema#>              |
| `schema:`    | <http://schema.org/>                                 |
| `service:`   | <http://purl.org/ontology/service#>                  |
| `shape:`     | <https://agriculture.ld.admin.ch/system-map/shapes/> |
| `systemmap:` | <https://agriculture.ld.admin.ch/system-map/>        |

</div>

## Datensatz

Informationseinheiten, die in IT-Systemen enthalten sind. Jeder
Datensatz liegt direkt oder über einen übergeordneten Datensatz in einem
IT-System. Gesondert ausgewiesen werden Stammdaten sowie Datensätze mit
Personendaten und mit besonders schützenswerten Personendaten.

### Übersicht

<div class="ech-facts">

IRI  
<https://agriculture.ld.admin.ch/system-map/shapes/Dataset>

Zielklasse  
`dcat:Dataset`

Geschlossen  
Ja (nur die aufgeführten Eigenschaften zulässig)

Kennzahlen  
127 Instanzen mit je 6 bis 32 Tripeln (im Mittel 11.3)

Open Data  
Ja ([auf LINDAS
publiziert](https://lindas.admin.ch/sparql/#query=PREFIX%20dcat%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0APREFIX%20dcterms%3A%20%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0APREFIX%20prov%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fprov%23%3E%0APREFIX%20rdfs%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0APREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0APREFIX%20systemmap%3A%20%3Chttps%3A%2F%2Fagriculture.ld.admin.ch%2Fsystem-map%2F%3E%0ASELECT%20%3Firi%20%3Fname%20%3Fabbreviation%20%3Fdescription%20%3Furl%20%3FseeAlso%20%3FcontainedIn%20%3FisPartOf%20%3FwasDerivedFrom%20%3Finforms%20%3FusesMasterData%20%3Fkeywords%20%3FhasLegalBasis%0AFROM%20%3Chttps%3A%2F%2Flindas.admin.ch%2Ffoag%2Fsystem-map%3E%0AWHERE%20%7B%0A%20%20%3Firi%20a%20dcat%3ADataset%20.%0A%20%20%3Firi%20schema%3Aname%20%3Fname%20.%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3Aabbreviation%20%3Fabbreviation%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Adescription%20%3Fdescription%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Aurl%20%3Furl%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20rdfs%3AseeAlso%20%3FseeAlso%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3AcontainedIn%20%3FcontainedIn%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20dcterms%3AisPartOf%20%3FisPartOf%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20prov%3AwasDerivedFrom%20%3FwasDerivedFrom%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3Ainforms%20%3Finforms%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3AusesMasterData%20%3FusesMasterData%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Akeywords%20%3Fkeywords%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3AhasLegalBasis%20%3FhasLegalBasis%20.%20%7D%0A%7D%0ALIMIT%201000))

</div>

### Eigenschaften

<table style="width:99%;">
<colgroup>
<col style="width: 39%" />
<col style="width: 45%" />
<col style="width: 13%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Beschreibung</th>
<th style="text-align: left;">Details</th>
<th style="text-align: right;">Kardinalität</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Name</strong>
(<code>schema:name</code>): Der bevorzugte Name, in mindestens einer der
Sprachen Deutsch, Französisch, Italienisch oder Englisch. Je Sprache ist
höchstens ein Name zulässig.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Länge: ≤ 125 Zeichen</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Abkürzung</strong>
(<code>systemmap:abbreviation</code>): Eine Abkürzung wird nur
angegeben, wenn sie nicht bereits der bevorzugte Name ist. Beispiel: Die
Fenaco Genossenschaft (fédération nationale des coopératives agricoles)
wird üblicherweise als “Fenaco” bezeichnet, sodass keine separate
Abkürzung erforderlich ist.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Beschreibung</strong>
(<code>schema:description</code>): Eine Beschreibung in Worten, je
Sprache höchstens eine.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Webseite</strong>
(<code>schema:url</code>): Eine Webseite mit weiteren
Informationen.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Siehe auch</strong>
(<code>rdfs:seeAlso</code>): Verweis auf eine weiterführende Quelle, zum
Beispiel eine Dokumentation oder eine Webseite.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>ist beinhaltet in</strong>
(<code>systemmap:containedIn</code>): Gibt an, dass eine
Informationseinheit X im IT-System Y enthalten ist. Beispielsweise sind
Informationen über landwirtschaftliche Flächen in der Schweiz in AGIS
enthalten.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-softwareapplication">IT-System</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>ist Teil von</strong>
(<code>dcterms:isPartOf</code>): Eine verwandte Ressource, in der die
beschriebene Ressource physisch oder logisch enthalten ist.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-dataset">Datensatz</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>wurde abgeleitet von</strong>
(<code>prov:wasDerivedFrom</code>): Eine Ableitung ist die
Transformation einer Entität in eine andere, eine Aktualisierung einer
Entität, die zu einer neuen führt, oder die Konstruktion einer neuen
Entität auf der Grundlage einer bereits existierenden.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-dataset">Datensatz</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>informiert</strong>
(<code>systemmap:informs</code>): Zeigt auf, dass Informationseinheit X
durch eine andere Informationseinheit Y informiert wird; d.h. dass
irgendwie Daten fliessen. Das kann über manuelles Abschreiben,
E-Mail-Versandt von Tabellen, APIs etc. geschehen.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-dataset">Datensatz</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>hat Masterdaten</strong>
(<code>systemmap:usesMasterData</code>): Gibt an, dass ein Datensatz
Stammdaten verwendet, zum Beispiel eine Betriebsnummer, über die er mit
anderen Datensätzen verknüpft ist.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-dataset">Datensatz</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Schlagwort</strong>
(<code>schema:keywords</code>): Ein Schlagwort, das den Gegenstand
thematisch einordnet.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-keyword">Schlagwort</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>hat Rechtsgrundlage</strong>
(<code>systemmap:hasLegalBasis</code>): Zeigt an, dass irgendetwas X
eine Rechtsgrundlage mit (einem bestimmten Teil) der Legislation Y
hat.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-legislation">Gesetzgebung</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
</tbody>
</table>

### Regeln (SPARQL)

#### Datensatz: Jeder Datensatz muss direkt oder über einen übergeordneten Datensatz in einem IT-System enthalten sein.

``` sparql
SELECT $this WHERE {
    FILTER NOT EXISTS {
        $this dcterms:isPartOf*/systemmap:containedIn ?system .
        ?system a schema:SoftwareApplication .
    }
}
```

## Gesetzgebung

Rechtsgrundlagen (Fedlex), auf die sich Organisationen, IT-Systeme und
Datensätze stützen. Ihre Namen sind die offiziellen Titel.

### Übersicht

<div class="ech-facts">

IRI  
<https://agriculture.ld.admin.ch/system-map/shapes/Legislation>

Zielklasse  
`schema:Legislation`

Geschlossen  
Ja (nur die aufgeführten Eigenschaften zulässig)

Kennzahlen  
49 Instanzen mit je 4 bis 7 Tripeln (im Mittel 5.6)

Open Data  
Ja ([auf LINDAS
publiziert](https://lindas.admin.ch/sparql/#query=PREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0APREFIX%20systemmap%3A%20%3Chttps%3A%2F%2Fagriculture.ld.admin.ch%2Fsystem-map%2F%3E%0ASELECT%20%3Firi%20%3Fname%20%3FalternateName%20%3Fabbreviation%0AFROM%20%3Chttps%3A%2F%2Flindas.admin.ch%2Ffoag%2Fsystem-map%3E%0AWHERE%20%7B%0A%20%20%3Firi%20a%20schema%3ALegislation%20.%0A%20%20%3Firi%20schema%3Aname%20%3Fname%20.%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3AalternateName%20%3FalternateName%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3Aabbreviation%20%3Fabbreviation%20.%20%7D%0A%7D%0ALIMIT%201000))

</div>

### Eigenschaften

<table style="width:99%;">
<colgroup>
<col style="width: 41%" />
<col style="width: 43%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Beschreibung</th>
<th style="text-align: left;">Details</th>
<th style="text-align: right;">Kardinalität</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Name</strong>
(<code>schema:name</code>): Der bevorzugte Name, in mindestens einer der
Sprachen Deutsch, Französisch, Italienisch oder Englisch. Je Sprache ist
höchstens ein Name zulässig.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Alternativer Name</strong>
(<code>schema:alternateName</code>): Eine weitere gebräuchliche
Bezeichnung, zum Beispiel ein früherer oder ein umgangssprachlicher
Name. Sie kann die Suche verbessern.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Abkürzung</strong>
(<code>systemmap:abbreviation</code>): Eine Abkürzung wird nur
angegeben, wenn sie nicht bereits der bevorzugte Name ist. Beispiel: Die
Fenaco Genossenschaft (fédération nationale des coopératives agricoles)
wird üblicherweise als “Fenaco” bezeichnet, sodass keine separate
Abkürzung erforderlich ist.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
</tbody>
</table>

## IT-Service

IT-Services, die von IT-Systemen bereitgestellt und von IT-Systemen oder
anderen Services genutzt werden.

### Übersicht

<div class="ech-facts">

IRI  
<https://agriculture.ld.admin.ch/system-map/shapes/Service>

Zielklasse  
`service:Service`

Geschlossen  
Ja (nur die aufgeführten Eigenschaften zulässig)

Kennzahlen  
10 Instanzen mit je 6 bis 77 Tripeln (im Mittel 14.2)

Open Data  
Ja ([auf LINDAS
publiziert](https://lindas.admin.ch/sparql/#query=PREFIX%20dcterms%3A%20%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0APREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0APREFIX%20service%3A%20%3Chttp%3A%2F%2Fpurl.org%2Fontology%2Fservice%23%3E%0ASELECT%20%3Firi%20%3Fname%20%3Fdescription%20%3Furl%20%3FprovidedBy%20%3Fconsumes%20%3FisPartOf%20%3Fkeywords%0AFROM%20%3Chttps%3A%2F%2Flindas.admin.ch%2Ffoag%2Fsystem-map%3E%0AWHERE%20%7B%0A%20%20%3Firi%20a%20service%3AService%20.%0A%20%20%3Firi%20schema%3Aname%20%3Fname%20.%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Adescription%20%3Fdescription%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Aurl%20%3Furl%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20service%3AprovidedBy%20%3FprovidedBy%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20service%3Aconsumes%20%3Fconsumes%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20dcterms%3AisPartOf%20%3FisPartOf%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Akeywords%20%3Fkeywords%20.%20%7D%0A%7D%0ALIMIT%201000))

</div>

### Eigenschaften

<table style="width:99%;">
<colgroup>
<col style="width: 39%" />
<col style="width: 45%" />
<col style="width: 13%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Beschreibung</th>
<th style="text-align: left;">Details</th>
<th style="text-align: right;">Kardinalität</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Name</strong>
(<code>schema:name</code>): Der bevorzugte Name, in mindestens einer der
Sprachen Deutsch, Französisch, Italienisch oder Englisch. Je Sprache ist
höchstens ein Name zulässig.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Länge: ≤ 125 Zeichen</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Beschreibung</strong>
(<code>schema:description</code>): Eine Beschreibung in Worten, je
Sprache höchstens eine.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Webseite</strong>
(<code>schema:url</code>): Eine Webseite mit weiteren
Informationen.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>wird bereitgestellt von</strong>
(<code>service:providedBy</code>): Zeigt an, dass ein technischer
Service von einem bestimmten IT-System bereitgestellt wird.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-softwareapplication">IT-System</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>nutzt IT-Service</strong>
(<code>service:consumes</code>): Zeigt an, dass ein beliebiges Objekt
(IT-System, Organisation etc.) einen bestimmten technischen IT-Service
nutzt.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-service">IT-Service</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>ist Teil von</strong>
(<code>dcterms:isPartOf</code>): Eine verwandte Ressource, in der die
beschriebene Ressource physisch oder logisch enthalten ist.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-service">IT-Service</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Schlagwort</strong>
(<code>schema:keywords</code>): Ein Schlagwort, das den Gegenstand
thematisch einordnet.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-keyword">Schlagwort</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
</tbody>
</table>

## IT-System

IT-Systeme, die Daten des Agrar- und Ernährungssektors verarbeiten.
Jedes IT-System hat eine deutsche Beschreibung und wird direkt oder über
ein übergeordnetes System von einer Organisation betrieben.
Farm-Management-Informationssysteme (FMIS) bilden eine eigene
Unterklasse.

### Übersicht

<div class="ech-facts">

IRI  
<https://agriculture.ld.admin.ch/system-map/shapes/SoftwareApplication>

Zielklasse  
`schema:SoftwareApplication`

Geschlossen  
Ja (nur die aufgeführten Eigenschaften zulässig)

Kennzahlen  
154 Instanzen mit je 6 bis 29 Tripeln (im Mittel 11.8)

Open Data  
Ja ([auf LINDAS
publiziert](https://lindas.admin.ch/sparql/#query=PREFIX%20dcterms%3A%20%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0APREFIX%20rdfs%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0APREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0APREFIX%20service%3A%20%3Chttp%3A%2F%2Fpurl.org%2Fontology%2Fservice%23%3E%0APREFIX%20systemmap%3A%20%3Chttps%3A%2F%2Fagriculture.ld.admin.ch%2Fsystem-map%2F%3E%0ASELECT%20%3Firi%20%3Fname%20%3FalternateName%20%3Fabbreviation%20%3Fdescription%20%3Furl%20%3FseeAlso%20%3FoperatedBy%20%3FdevelopedBy%20%3Fconsumes%20%3FisPartOf%20%3Fkeywords%20%3FhasLegalBasis%0AFROM%20%3Chttps%3A%2F%2Flindas.admin.ch%2Ffoag%2Fsystem-map%3E%0AWHERE%20%7B%0A%20%20%3Firi%20a%20schema%3ASoftwareApplication%20.%0A%20%20%3Firi%20schema%3Aname%20%3Fname%20.%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3AalternateName%20%3FalternateName%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3Aabbreviation%20%3Fabbreviation%20.%20%7D%0A%20%20%3Firi%20schema%3Adescription%20%3Fdescription%20.%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Aurl%20%3Furl%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20rdfs%3AseeAlso%20%3FseeAlso%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3AoperatedBy%20%3FoperatedBy%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3AdevelopedBy%20%3FdevelopedBy%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20service%3Aconsumes%20%3Fconsumes%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20dcterms%3AisPartOf%20%3FisPartOf%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Akeywords%20%3Fkeywords%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3AhasLegalBasis%20%3FhasLegalBasis%20.%20%7D%0A%7D%0ALIMIT%201000))

</div>

### Eigenschaften

<table style="width:99%;">
<colgroup>
<col style="width: 39%" />
<col style="width: 45%" />
<col style="width: 13%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Beschreibung</th>
<th style="text-align: left;">Details</th>
<th style="text-align: right;">Kardinalität</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Name</strong>
(<code>schema:name</code>): Der bevorzugte Name, in mindestens einer der
Sprachen Deutsch, Französisch, Italienisch oder Englisch. Je Sprache ist
höchstens ein Name zulässig.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Länge: ≤ 125 Zeichen</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Alternativer Name</strong>
(<code>schema:alternateName</code>): Eine weitere gebräuchliche
Bezeichnung, zum Beispiel ein früherer oder ein umgangssprachlicher
Name. Sie kann die Suche verbessern.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Abkürzung</strong>
(<code>systemmap:abbreviation</code>): Eine Abkürzung wird nur
angegeben, wenn sie nicht bereits der bevorzugte Name ist. Beispiel: Die
Fenaco Genossenschaft (fédération nationale des coopératives agricoles)
wird üblicherweise als “Fenaco” bezeichnet, sodass keine separate
Abkürzung erforderlich ist.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Beschreibung</strong>
(<code>schema:description</code>): Eine Beschreibung in Worten, je
Sprache höchstens eine.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Webseite</strong>
(<code>schema:url</code>): Eine Webseite mit weiteren
Informationen.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Siehe auch</strong>
(<code>rdfs:seeAlso</code>): Verweis auf eine weiterführende Quelle, zum
Beispiel eine Dokumentation oder eine Webseite.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>wird betrieben von</strong>
(<code>systemmap:operatedBy</code>): Gibt an, dass ein IT-System X durch
eine Organisation Y betrieben wird. Das bedeutet, dass die Organisation
Y für den Betrieb von System X zuständig ist.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-organization">Organisation</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>entwickelt von</strong>
(<code>systemmap:developedBy</code>): Gibt an, dass ein IT-System von
einer Organisation entwickelt wird oder wurde.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-organization">Organisation</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>nutzt IT-Service</strong>
(<code>service:consumes</code>): Zeigt an, dass ein beliebiges Objekt
(IT-System, Organisation etc.) einen bestimmten technischen IT-Service
nutzt.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-service">IT-Service</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>ist Teil von</strong>
(<code>dcterms:isPartOf</code>): Eine verwandte Ressource, in der die
beschriebene Ressource physisch oder logisch enthalten ist.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-softwareapplication">IT-System</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Schlagwort</strong>
(<code>schema:keywords</code>): Ein Schlagwort, das den Gegenstand
thematisch einordnet.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-keyword">Schlagwort</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>hat Rechtsgrundlage</strong>
(<code>systemmap:hasLegalBasis</code>): Zeigt an, dass irgendetwas X
eine Rechtsgrundlage mit (einem bestimmten Teil) der Legislation Y
hat.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-legislation">Gesetzgebung</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
</tbody>
</table>

### Regeln (SPARQL)

#### IT-System: Eine deutsche Beschreibung ist Pflicht.

``` sparql
SELECT $this WHERE {
    FILTER NOT EXISTS {
        $this schema:description ?description .
        FILTER(LANG(?description) = "de")
    }
}
```

#### IT-System: Jedes IT-System muss direkt oder über ein übergeordnetes System von einer Organisation betrieben werden.

``` sparql
SELECT $this WHERE {
    FILTER NOT EXISTS {
        $this dcterms:isPartOf*/systemmap:operatedBy ?organization .
        ?organization a schema:Organization .
    }
}
```

## Organisation

Organisationen der Verwaltung und der Privatwirtschaft, die IT-Systeme
betreiben, besitzen oder entwickeln. Unterschieden werden Organisationen
des Bundes, kantonale Organisationen (darunter Landwirtschaftsämter,
Veterinärdienste und Beratungsstellen der Kantone) und privatrechtliche
Organisationen.

### Übersicht

<div class="ech-facts">

IRI  
<https://agriculture.ld.admin.ch/system-map/shapes/Organization>

Zielklasse  
`schema:Organization`

Geschlossen  
Ja (nur die aufgeführten Eigenschaften zulässig)

Kennzahlen  
270 Instanzen mit je 5 bis 40 Tripeln (im Mittel 11.3)

Open Data  
Ja ([auf LINDAS
publiziert](https://lindas.admin.ch/sparql/#query=PREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0APREFIX%20systemmap%3A%20%3Chttps%3A%2F%2Fagriculture.ld.admin.ch%2Fsystem-map%2F%3E%0ASELECT%20%3Firi%20%3Fname%20%3Fabbreviation%20%3Fdescription%20%3Furl%20%3FsameAs%20%3FparentOrganization%20%3FmemberOf%20%3Fowns%20%3Faccess%20%3FhasLegalBasis%0AFROM%20%3Chttps%3A%2F%2Flindas.admin.ch%2Ffoag%2Fsystem-map%3E%0AWHERE%20%7B%0A%20%20%3Firi%20a%20schema%3AOrganization%20.%0A%20%20%3Firi%20schema%3Aname%20%3Fname%20.%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3Aabbreviation%20%3Fabbreviation%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Adescription%20%3Fdescription%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3Aurl%20%3Furl%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3AsameAs%20%3FsameAs%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3AparentOrganization%20%3FparentOrganization%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20schema%3AmemberOf%20%3FmemberOf%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3Aowns%20%3Fowns%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3Aaccess%20%3Faccess%20.%20%7D%0A%20%20OPTIONAL%20%7B%20%3Firi%20systemmap%3AhasLegalBasis%20%3FhasLegalBasis%20.%20%7D%0A%7D%0ALIMIT%201000))

</div>

### Eigenschaften

<table style="width:99%;">
<colgroup>
<col style="width: 40%" />
<col style="width: 43%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Beschreibung</th>
<th style="text-align: left;">Details</th>
<th style="text-align: right;">Kardinalität</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Name</strong>
(<code>schema:name</code>): Der bevorzugte Name, in mindestens einer der
Sprachen Deutsch, Französisch, Italienisch oder Englisch. Je Sprache ist
höchstens ein Name zulässig.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Länge: ≤ 125 Zeichen</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Abkürzung</strong>
(<code>systemmap:abbreviation</code>): Eine Abkürzung wird nur
angegeben, wenn sie nicht bereits der bevorzugte Name ist. Beispiel: Die
Fenaco Genossenschaft (fédération nationale des coopératives agricoles)
wird üblicherweise als “Fenaco” bezeichnet, sodass keine separate
Abkürzung erforderlich ist.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Beschreibung</strong>
(<code>schema:description</code>): Eine Beschreibung in Worten, je
Sprache höchstens eine.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Webseite</strong>
(<code>schema:url</code>): Eine Webseite mit weiteren
Informationen.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Registereintrag</strong>
(<code>schema:sameAs</code>): Verweis auf den Eintrag derselben
Organisation in einem amtlichen Register, etwa im Staatskalender oder im
Handelsregister (Zefix). Die Angaben des Registers werden nicht
kopiert.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>gehört zu</strong>
(<code>schema:parentOrganization</code>): Zeigt an, dass die
(Teil-)Organisation ein Teil von einer (Über-)Organisation Y ist.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-organization">Organisation</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Mitglied von</strong>
(<code>schema:memberOf</code>): Gibt an, dass eine Organisation X eine
Mitgliedsorganisation einer anderen Organisation Y ist. Die Beziehung
soll Mitgliedschaften von Branchenorganisationen, Berufsverbänden oder
anderen formellen Vereinigungen darstellen, bei denen Organisationen als
Mitglieder teilnehmen. Informelle Beziehungen gehören nicht dazu.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-organization">Organisation</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>besitzt (teilweise)</strong>
(<code>systemmap:owns</code>): Diese Beziehung zeigt an, dass eine
Organisation X eine andere Organisation Y (teilweise) besitzt.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-organization">Organisation</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>hat Zugriff auf</strong>
(<code>systemmap:access</code>): Zeigt an, dass eine Organisation X die
Rechte zum Zugriff etwas hat.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">0..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>hat Rechtsgrundlage</strong>
(<code>systemmap:hasLegalBasis</code>): Zeigt an, dass irgendetwas X
eine Rechtsgrundlage mit (einem bestimmten Teil) der Legislation Y
hat.</td>
<td style="text-align: left;"><ul>
<li>Typ: <a href="#sec-nodeshape-legislation">Gesetzgebung</a></li>
</ul></td>
<td style="text-align: right;">0..*</td>
</tr>
</tbody>
</table>

## Schlagwort

Schlagwörter zur thematischen Einordnung.

### Übersicht

<div class="ech-facts">

IRI  
<https://agriculture.ld.admin.ch/system-map/shapes/Keyword>

Zielklasse  
`schema:DefinedTerm`

Geschlossen  
Ja (nur die aufgeführten Eigenschaften zulässig)

Kennzahlen  
20 Instanzen mit je 7 Tripeln

Open Data  
Ja ([auf LINDAS
publiziert](https://lindas.admin.ch/sparql/#query=PREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0ASELECT%20%3Firi%20%3Fname%0AFROM%20%3Chttps%3A%2F%2Flindas.admin.ch%2Ffoag%2Fsystem-map%3E%0AWHERE%20%7B%0A%20%20%3Firi%20a%20schema%3ADefinedTerm%20.%0A%20%20%3Firi%20schema%3Aname%20%3Fname%20.%0A%7D%0ALIMIT%201000))

</div>

### Eigenschaften

<table style="width:99%;">
<colgroup>
<col style="width: 41%" />
<col style="width: 43%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Beschreibung</th>
<th style="text-align: left;">Details</th>
<th style="text-align: right;">Kardinalität</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Name</strong>
(<code>schema:name</code>): Der bevorzugte Name, in mindestens einer der
Sprachen Deutsch, Französisch, Italienisch oder Englisch. Je Sprache ist
höchstens ein Name zulässig.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Länge: ≤ 125 Zeichen</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
</tbody>
</table>

## Subgraph

Subgraphen, die einen thematischen Ausschnitt der Systemlandkarte
zusammenfassen.

### Übersicht

<div class="ech-facts">

IRI  
<https://agriculture.ld.admin.ch/system-map/shapes/Subgraph>

Zielklasse  
`dcmitype:Collection`

Geschlossen  
Ja (nur die aufgeführten Eigenschaften zulässig)

Kennzahlen  
6 Instanzen mit je 31 bis 143 Tripeln (im Mittel 69.7)

Open Data  
Ja ([auf LINDAS
publiziert](https://lindas.admin.ch/sparql/#query=PREFIX%20dcmitype%3A%20%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fdcmitype%2F%3E%0APREFIX%20schema%3A%20%3Chttp%3A%2F%2Fschema.org%2F%3E%0APREFIX%20systemmap%3A%20%3Chttps%3A%2F%2Fagriculture.ld.admin.ch%2Fsystem-map%2F%3E%0ASELECT%20%3Firi%20%3Fname%20%3FcontainsNodes%0AFROM%20%3Chttps%3A%2F%2Flindas.admin.ch%2Ffoag%2Fsystem-map%3E%0AWHERE%20%7B%0A%20%20%3Firi%20a%20dcmitype%3ACollection%20.%0A%20%20%3Firi%20schema%3Aname%20%3Fname%20.%0A%20%20%3Firi%20systemmap%3AcontainsNodes%20%3FcontainsNodes%20.%0A%7D%0ALIMIT%201000))

</div>

### Eigenschaften

<table style="width:99%;">
<colgroup>
<col style="width: 41%" />
<col style="width: 43%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Beschreibung</th>
<th style="text-align: left;">Details</th>
<th style="text-align: right;">Kardinalität</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Name</strong>
(<code>schema:name</code>): Der bevorzugte Name, in mindestens einer der
Sprachen Deutsch, Französisch, Italienisch oder Englisch. Je Sprache ist
höchstens ein Name zulässig.</td>
<td style="text-align: left;"><ul>
<li>Typ: Sprachabhängiger Text (<code>rdf:langString</code>)</li>
<li>Länge: ≤ 125 Zeichen</li>
<li>Sprachen: <code>de</code>, <code>fr</code>, <code>it</code>,
<code>en</code> (eine pro Sprache)</li>
</ul></td>
<td style="text-align: right;">1..*</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Elemente in diesem
Subgraph</strong> (<code>systemmap:containsNodes</code>): Ein Element,
das zu diesem Subgraphen gehört: ein IT-System, ein Datensatz, ein
Service oder eine Organisation.</td>
<td style="text-align: left;"></td>
<td style="text-align: right;">1..*</td>
</tr>
</tbody>
</table>

# Anhang A – Referenzen

<div id="refs" class="references csl-bib-body">

<div id="ref-SHACL" class="csl-entry">

<span class="csl-left-margin">\[SHACL\]
</span><span class="csl-right-inline">Knublauch, Holger ; Kontokostas,
Dimitris: *[Shapes Constraint Language
(SHACL)](https://www.w3.org/TR/shacl/)* (W3C Recommendation) : World
Wide Web Consortium (W3C), 2017</span>

</div>

<div id="ref-SPARQL" class="csl-entry">

<span class="csl-left-margin">\[SPARQL\]
</span><span class="csl-right-inline">Harris, Steve ; Seaborne, Andy:
*[SPARQL 1.1 Query Language](https://www.w3.org/TR/sparql11-query/)*
(W3C Recommendation) : World Wide Web Consortium (W3C), 2013</span>

</div>

</div>

# Anhang B – Mitwirkung

<div id="tbl-authors">

Tabelle 5: Mitwirkende

| Name              | Organisation                 |
|:------------------|:-----------------------------|
| Marc Beringer     | Bundesamt für Landwirtschaft |
| Linus Degen       | Berner Fachhochschule        |
| Pascal Hurni      | Bundesamt für Landwirtschaft |
| Damian Oswald     | Bundesamt für Landwirtschaft |
| Michael Schüpbach | Bundesamt für Landwirtschaft |
| Lea Stauber       | Bundesamt für Landwirtschaft |

</div>

# Anhang C – Abkürzungen und Glossar

Dieses Glossar ist auch maschinenlesbar verfügbar, auf LINDAS und im
Repository unter `src/rdf/data/glossary.skos.ttl`.

<div id="tbl-glossary">

Tabelle 6: Glossar der Systemlandkarte

<table>
<colgroup>
<col style="width: 35%" />
<col style="width: 65%" />
</colgroup>
<thead>
<tr>
<th style="text-align: left;">Begriff</th>
<th style="text-align: left;">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><strong>Datensatz</strong></td>
<td style="text-align: left;"><p>Eine Informationseinheit, die in einem
IT-System enthalten ist, zum Beispiel eine Datenbank, eine Tabelle oder
ein Dokument.</p>
<p><em>Verwandt</em>: IT-System</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Graph</strong> (Named Graph)</td>
<td style="text-align: left;"><p>Eine Menge von Tripeln. Ein benannter
Graph wird selbst durch eine IRI identifiziert und erlaubt es, Daten in
einem Triple Store zu gruppieren.</p>
<p><em>Oberbegriff</em>: Resource Description Framework</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Inferenz</strong> (Reasoning)</td>
<td style="text-align: left;">Das automatische Ableiten neuer Aussagen
aus den vorhandenen Daten und den Axiomen einer Ontologie, zum Beispiel
durch den Reasoner HermiT.</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Internationalized Resource
Identifier</strong> (IRI)</td>
<td style="text-align: left;"><p>Weltweit eindeutiger Bezeichner einer
Ressource. In RDF werden Subjekte, Prädikate und die meisten Objekte
durch IRIs identifiziert.</p>
<p><em>Oberbegriff</em>: Resource Description Framework</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>IT-Service</strong></td>
<td style="text-align: left;"><p>Eine technische Softwarekomponente, die
über klar definierte Schnittstellen Funktionen für andere Systeme
bereitstellt.</p>
<p><em>Verwandt</em>: IT-System</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>IT-System</strong></td>
<td style="text-align: left;">Eine eigenständige Anwendung, die Daten
verarbeitet, oft mit einer oder mehreren dazugehörigen Datenbanken, und
von einer Organisation betrieben wird.</td>
</tr>
<tr>
<td style="text-align: left;"><strong>JSON for Linking Data</strong>
(JSON-LD)</td>
<td style="text-align: left;"><p>Eine Serialisierung von RDF auf der
Basis von JSON, die sich besonders für Web-Schnittstellen eignet.</p>
<p><em>Oberbegriff</em>: Serialisierung</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Linked Data</strong> (Verknüpfte
Daten)</td>
<td style="text-align: left;"><p>Daten, die nach den Prinzipien des
Semantic Web mit IRIs identifiziert, in RDF beschrieben und
untereinander verknüpft publiziert werden.</p>
<p><em>Verwandt</em>: Linked Data Service, Resource Description
Framework</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Linked Data Service</strong>
(LINDAS)</td>
<td style="text-align: left;">Der offizielle Linked-Data-Dienst der
Schweizer Bundesverwaltung, der als Triple Store fungiert.</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Literal</strong></td>
<td style="text-align: left;"><p>Ein konkreter Wert in RDF, etwa eine
Zeichenkette, eine Zahl oder ein Datum, optional mit Datentyp oder
Sprachangabe.</p>
<p><em>Oberbegriff</em>: Resource Description Framework</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Namensraum</strong> (Präfix)</td>
<td style="text-align: left;"><p>Gemeinsamer Anfang einer Gruppe von
IRIs. In Turtle und SPARQL wird ein Namensraum durch ein Präfix
abgekürzt, zum Beispiel <code>schema:</code> für
<code>http://schema.org/</code>.</p>
<p><em>Verwandt</em>: Internationalized Resource Identifier</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Ontologie</strong></td>
<td style="text-align: left;"><p>Ein formales Modell eines Fachgebiets,
das Klassen, Eigenschaften und deren logische Beziehungen so beschreibt,
dass Maschinen daraus Schlüsse ziehen können.</p>
<p><em>Oberbegriff</em>: Vokabular</p>
<p><em>Verwandt</em>: Web Ontology Language</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Resource Description
Framework</strong> (RDF)</td>
<td style="text-align: left;">Ein zentraler Standard des World Wide Web
Consortiums (W3C) zur Modellierung von Datenstrukturen im Web.
Informationen werden nicht in klassischen Tabellen, sondern als
vernetzte Graphen abgebildet.</td>
</tr>
<tr>
<td style="text-align: left;"><strong>Serialisierung</strong></td>
<td style="text-align: left;"><p>Textuelle Darstellung eines RDF-Graphen
in einem definierten Format, um ihn zu speichern oder auszutauschen.</p>
<p><em>Unterbegriff</em>: JSON for Linking Data, Terse RDF Triple
Language</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Shape</strong></td>
<td style="text-align: left;"><p>Eine Menge von Bedingungen, die eine
Klasse von Ressourcen oder eine Eigenschaft erfüllen muss, etwa
Pflichtfelder, Datentypen und Kardinalitäten.</p>
<p><em>Oberbegriff</em>: Shapes Constraint Language</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Shapes Constraint
Language</strong> (SHACL)</td>
<td style="text-align: left;"><p>Die Sprache des W3C zur Beschreibung
und Prüfung der Struktur von RDF-Daten. Das Datenmodell dieses Standards
ist in SHACL formuliert.</p>
<p><em>Unterbegriff</em>: Shape</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Simple Knowledge Organization
System</strong> (SKOS)</td>
<td style="text-align: left;"><p>Ein Vokabular des W3C für Thesauri,
Klassifikationen und Glossare. Dieses Glossar ist selbst in SKOS
erfasst.</p>
<p><em>Verwandt</em>: Vokabular</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>SPARQL Protocol and RDF Query
Language</strong> (SPARQL)</td>
<td style="text-align: left;"><p>Die Abfragesprache des W3C für
RDF-Daten. Mit SPARQL werden Daten aus Graphen gelesen, verändert und
zwischen Systemen ausgetauscht.</p>
<p><em>Verwandt</em>: Resource Description Framework</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>SPARQL-Endpunkt</strong></td>
<td style="text-align: left;"><p>Eine Web-Schnittstelle, über die
SPARQL-Abfragen an einen Triple Store gesendet werden können.</p>
<p><em>Oberbegriff</em>: SPARQL Protocol and RDF Query Language</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Stammdaten</strong></td>
<td style="text-align: left;"><p>Grundlegende Daten, die von vielen
Systemen gemeinsam genutzt werden und sich selten ändern, etwa die
Identifikatoren von Betrieben oder Unternehmen.</p>
<p><em>Verwandt</em>: Datensatz</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Subgraph</strong></td>
<td style="text-align: left;"><p>Ein thematischer Ausschnitt der
Systemlandkarte, zum Beispiel die Architektur rund um ein System.</p>
<p><em>Verwandt</em>: Graph</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Terse RDF Triple Language</strong>
(Turtle)</td>
<td style="text-align: left;"><p>Eine kompakte, gut lesbare
Serialisierung für RDF. Alle RDF-Dateien dieses Standards sind in Turtle
verfasst.</p>
<p><em>Oberbegriff</em>: Serialisierung</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Tripel</strong></td>
<td style="text-align: left;"><p>Die Grundstruktur einer Aussage in RDF,
bestehend aus Subjekt, Prädikat und Objekt.</p>
<p><em>Oberbegriff</em>: Resource Description Framework</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Triple Store</strong>
(Graphdatenbank)</td>
<td style="text-align: left;"><p>Eine Datenbank, die auf das Speichern
und Abfragen von RDF-Tripeln spezialisiert ist.</p>
<p><em>Verwandt</em>: Linked Data Service</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Vokabular</strong></td>
<td style="text-align: left;"><p>Eine Sammlung von Klassen und
Eigenschaften mit festgelegter Bedeutung, die zur Beschreibung von Daten
wiederverwendet wird, zum Beispiel schema.org.</p>
<p><em>Unterbegriff</em>: Ontologie</p></td>
</tr>
<tr>
<td style="text-align: left;"><strong>Web Ontology Language</strong>
(OWL)</td>
<td style="text-align: left;"><p>Die Sprache des W3C zur Formulierung
von Ontologien. Sie erlaubt es, Klassen und Eigenschaften mit logischen
Axiomen zu definieren.</p>
<p><em>Verwandt</em>: Inferenz</p></td>
</tr>
</tbody>
</table>

</div>

# Anhang D – Änderungen gegenüber dem bisherigen Repository

Die Systemlandkarte wurde bisher im Repository
[system-map](https://github.com/blw-ofag-ufag/system-map) gepflegt. Mit
dem Wechsel in das vorliegende Repository blieb die vollständige
Versionsgeschichte erhalten.

# Anhang E – Tabellenverzeichnis
