
![Build Status](https://github.com/INF-UFRGS-Ontologies/OFL/actions/workflows/qc.yml/badge.svg)
# Ontology of Functional Locations

Description: A BFO-compliant ontology for modeling functional locations as persistent spatial sites in industrial asset management systems, based on the Ontology Design Pattern developed by Santos et al. (2026). The pattern separates five concerns: spatial site (bfo:Site), organizational code (iao:CentrallyRegisteredIdentifier), equipment tag (iao:CentrallyRegisteredIdentifier), functional specification (iao:DirectiveInformationEntity), and installed equipment (iof:MaterialArtifact). Both identifiers denote the functional location site, not the physical equipment — the relationship to equipment is always mediated through the site.

More information can be found at http://obofoundry.org/ontology/ofl

## Versions

### Stable release versions

The latest version of the ontology can always be found at:

https://www.inf.ufrgs.br/ontologies/ofl.owl

(note this will not show up until the request has been approved by obofoundry.org)

### Editors' version

Editors of this ontology should use the edit version, [src/ontology/ofl-edit.owl](src/ontology/ofl-edit.owl)

## Contact

Please use this GitHub repository's [Issue tracker](https://github.com/INF-UFRGS-Ontologies/OFL/issues) to request new terms/classes or report errors or specific concerns related to the ontology.

## Acknowledgements

This ontology repository was created using the [Ontology Development Kit (ODK)](https://github.com/INCATools/ontology-development-kit).