# XEMO: Construction Site Emission Management Ontology

XEMO is an ontology for the semantic representation of construction-site pollutant emission monitoring and management. It provides a shared structure for connecting construction-site organisation, emission sources, pollutants, sensors, observations, and thresholds, supporting the development of interoperable Semantic Digital Twin applications.

The current version focuses on particulate matter (PM) and on the alerting use case, particularly the identification of threshold exceedances and their traceability to the relevant construction area and emission source.

## Ontology file

The ontology is available in Turtle format:

- [`xemo.ttl`](xemo.ttl)

Current development namespace:

```text
https://example.org/xemo#
```

## Scope

XEMO represents:

- an urban region containing one or more construction sites;
- construction sites organised into construction areas;
- construction activities carried out within those areas;
- sites, areas, and activities as emission sources at different spatial and operational scales;
- pollutants as observable properties of emission sources;
- sensors, platforms, deployments, and observations;
- thresholds defined by value, unit, type, averaging period, statistical method, and regulatory provenance.

The current implementation includes PM10, PM2.5, and total suspended particles, together with example threshold definitions derived from Directive (EU) 2024/2881.

## Main modelling approach

Construction sites, construction areas, and construction activities are modelled as subclasses of `xemo:EmissionSource`. Since `xemo:EmissionSource` is aligned with `sosa:FeatureOfInterest`, observations can be explicitly associated with the site, area, or activity to which they refer.

Pollutants are represented as subclasses or instances of `xemo:Pollutant`, which is aligned with `sosa:ObservableProperty`. Thresholds are represented as explicit entities and linked to pollutants, quantitative values, units, averaging periods, statistical methods, threshold types, and regulatory sources.

This structure supports the semantic integration of monitoring observations with their spatial, operational, and regulatory context.

## Reused ontologies

XEMO selectively reuses established vocabularies:

| Ontology | Role in XEMO |
| --- | --- |
| [BOT](https://w3id.org/bot) | Construction-site spatial organisation and topological relations |
| [SOSA/SSN](https://www.w3.org/TR/vocab-ssn/) | Sensors, platforms, deployments, observations, and features of interest |
| [QUDT](https://www.qudt.org/) | Quantitative values and units of measure |
| [OWL-Time](https://www.w3.org/TR/owl-time/) | Temporal descriptions and averaging periods |
| [PROV-O](https://www.w3.org/TR/prov-o/) | Provenance of thresholds and other entities |
| [Digital Construction Processes](https://w3id.org/digitalconstruction/0.5/Processes) | Construction activities and process semantics |

## Evaluation and demonstrator

The ontology was initially evaluated through two competency questions:

1. Can PM threshold exceedances be detected from sensor observations?
2. Can PM threshold exceedances be traced to the relevant construction area and emission source?

A separate demonstrator generates synthetic PM observations, integrates them into a XEMO-based knowledge graph, and performs recurrent SHACL validation for threshold exceedance detection:

- [XEMO PM SHACL Alerting Demonstrator](https://github.com/AlessandroBruttini/XEMO-PM-SHACL-Alerting-demonstrator)

## Use

The ontology can be opened and inspected with an OWL editor such as [Protégé](https://protege.stanford.edu/) or loaded into an RDF/OWL-compatible triplestore or application.

XEMO is currently a research ontology under development. Its present scope concentrates on PM monitoring and threshold-based alerting. Further work will extend its coverage of other pollutants, urban context, exposed receptors, mitigation actions, planning, and additional Semantic Digital Twin services.

## Related publication

Bruttini, A., Hagedorn, P., Getuli, V., Capone, P., and König, M. (2026). *XEMO: Construction Site Emission Management Ontology for Particulate Matter*. EG-ICE 2026.

Complete publication details and a DOI will be added when available.

## Licence

The contents of this repository are licensed under the [Creative Commons Attribution 4.0 International Licence](LICENSE).

You may share and adapt the material for any purpose, including commercial use, provided that appropriate credit is given, a link to the licence is supplied, and any changes are indicated.

Suggested attribution:

> XEMO: Construction Site Emission Management Ontology, Alessandro Bruttini, Philipp Hagedorn, Vito Getuli, Pietro Capone, and Markus König, licensed under CC BY 4.0.

## Contact

Alessandro Bruttini  
Department of Architecture, University of Florence  
alessandro.bruttini@unifi.it
