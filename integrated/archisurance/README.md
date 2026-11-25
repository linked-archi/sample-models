# ArchiSurance

The Open Group's ArchiSurance case study as one Linked.Archi graph: the case's ArchiMate model joined with its
business processes in BPMN, sequence and component diagrams in PlantUML, a LeanIX portfolio and a Backstage
catalog. Each source is converted to RDF in a named graph of its own and linked to the ArchiMate elements it
describes. ArchiSurance is a fictitious insurer.

| | |
| --- | --- |
| RDF | `archisurance.trig` |
| ArchiMate model | `archisurance.xml`, in the ArchiMate Exchange Format: the file the graph's ArchiMate part was converted from. `archisurance.archimate`, the same model as an Archi model, imported from it by Archi 5.7.0 |
| Upstream | `upstream/ArchiSurance-3.1-revised.exchange.xml`, The Open Group's Exchange Format file, unmodified (SHA-256 `b28d410d…637b741`) |
| Languages | ArchiMate 3.1, BPMN 2.0, UML (PlantUML), LeanIX, Backstage |
| Base IRI | `https://linked.archi/examples/archisurance/` |
| Made from | The sources and the pipeline that joins them, in [linked-archi/examples/archisurance](https://gitlab.com/linked-archi/examples/archisurance) on GitLab: the ArchiMate Exchange Format model, BPMN 2.0 processes, PlantUML diagrams, a LeanIX workspace export and Backstage catalog descriptors |
| Licence | [CC BY-SA 4.0](LICENSE.md), adapted from The Open Group's *ArchiSurance Case Study* v3.1 (CC BY-SA 3.0): see [NOTICE.md](NOTICE.md) |

The graph also records its provenance: the source commits and files each named graph was converted from.

`archisurance.xml` is the Linked.Archi edition of the case study's model: The Open Group's Exchange Format file,
the one in `upstream/`, with an `@id` property on every named element, which gives it a global identifier, and the fixes listed in
[CHANGES.md](https://gitlab.com/linked-archi/examples/archisurance/models/archimate/-/blob/main/CHANGES.md). Any
tool that imports the Exchange Format shows these as ordinary properties.
