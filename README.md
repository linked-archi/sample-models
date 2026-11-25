# Linked.Archi sample models

Architecture models in [Linked.Archi](https://meta.linked.archi/) RDF, for trying the tools.

## One language each

Small, invented models, each in one modelling language, all but the payment platform with views. Every name,
organisation and address in them is made up; the IRIs are under `example.org`.

| Model | Language | RDF | Base IRI | Made from |
| --- | --- | --- | --- | --- |
| [Acme online shop](archimate4/acme-shop/) | ArchiMate 4 | `acme-shop.ttl` | `https://example.org/acme/shop/` | drawn in la-gram |
| [Payment platform](archimate3/payment-platform/) | ArchiMate 3.2 | `payment-platform.trig` | `https://example.org/la/` | `payment-platform.xml`, ArchiMate Exchange Format |
| [Order domain](bpmn/order-domain/) | BPMN 2.0 | `order-domain.trig` | `https://example.org/la/` | two BPMN processes, one view each |
| [Shop](uml/shop/) | UML | `shop.trig` | `https://example.org/la/` | three PlantUML diagrams sharing their classes |

The RDF files are what the tools read. The files beside them are the inputs a Linked.Archi converter made them
from: the source diagrams, `diagram-index.yaml`, which collects a model's diagrams as its views, and
`identity-lock.yaml`, which keeps the IRIs the same from one conversion to the next.

## Several languages, one graph

Two case studies, each a graph that joins models in several languages: every source converted to RDF in a
named graph of its own, linked to the others. Their sources and the pipelines that join them are in
[linked-archi/examples](https://gitlab.com/linked-archi/examples) on GitLab.

| Model | Languages | RDF | Base IRI | Licence |
| --- | --- | --- | --- | --- |
| [ArchiSurance](integrated/archisurance/) | ArchiMate 3.1, BPMN 2.0, UML (PlantUML), LeanIX, Backstage | `archisurance.trig` | `https://linked.archi/examples/archisurance/` | CC BY-SA 4.0, adapted from The Open Group's case study |
| [VIO Group](integrated/vio/) | ArchiMate 3.2, C4, BPMN 2.0, LeanIX, Backstage, decision records | `vio.trig` | `https://linked.archi/examples/vio/` | CC BY-SA 4.0 |

Beside each graph is its ArchiMate model, in the ArchiMate Exchange Format (`.xml`), the file the graph's
ArchiMate part was converted from, and as an Archi model (`.archimate`).

ArchiSurance is The Open Group's fictitious insurer; VIO Group is a fictional tour operator. Each folder's
`LICENSE.md` states its terms, which apply to documentation generated from it too.

## Documentation from a model

[rdf2docs](https://github.com/linked-archi/rdf2docs) generates a static site from a model — a page at every
IRI, the views drawn in their notation, a graph, SPARQL and the RDF — and an AI context document:

```bash
curl -fsSLO https://raw.githubusercontent.com/linked-archi/sample-models/main/archimate4/acme-shop/acme-shop.ttl
docker run --rm -v "$PWD:/work" -w /work ghcr.io/linked-archi/rdf2docs \
  rdf2docs generate --input acme-shop.ttl --output-dir site --base https://example.org/acme/shop/
```

Open `site/html/index.html`. rdf2docs' `playground/run-sample.sh` does the same for every model here, and
[its demo](https://linked-archi.github.io/rdf2docs/) shows the result.
