
![Build Status](https://github.com/INF-UFRGS-Ontologies/OFL/actions/workflows/qc.yml/badge.svg)
# Ontology of Functional Locations

Description: A BFO-compliant ontology for modeling functional locations as persistent spatial sites in industrial asset management systems, based on the Ontology Design Pattern developed by Santos et al. (2026). The pattern separates five concerns: spatial site (bfo:Site), organizational code (iao:CentrallyRegisteredIdentifier), equipment tag (iao:CentrallyRegisteredIdentifier), functional specification (iao:DirectiveInformationEntity), and installed equipment (iof:MaterialArtifact). Both identifiers denote the functional location site, not the physical equipment — the relationship to equipment is always mediated through the site.

---

The Ontology of Functional Location models **functional locations** — the persistent positions in an industrial plant where maintainable equipment is or can be installed — as instances of `bfo:Site`, a spatial continuant whose boundaries are determined by surrounding material structures rather than by the equipment that may occupy the position.  This grounds the key industrial requirement that a functional location *persists when empty*: when a sensor is removed, the mounting flange and cable conduit remain, so the site boundaries remain anchored.

The ontology **separates five concerns**:

| Element | OWL class | Role |
|---|---|---|
| **Spatial site** | `fl:FunctionalLocation` (⊑ `bfo:Site`) | The persistent position; the integration key for all other elements |
| **Organizational code** | `fl:FunctionalLocationCode` (⊑ `iao:CentrallyRegisteredIdentifier`) | Encodes WHERE in the ISO 14224 hierarchy (e.g., `30234.FSFS.FWSF.10.01.01`) |
| **Equipment tag** | `fl:EquipmentTag` (⊑ `iao:CentrallyRegisteredIdentifier`) | Encodes WHAT type of equipment is expected (e.g., `PT-23424`); denotes the **site**, not the equipment |
| **Functional specification** | `fl:FunctionalLocationSpecification` (⊑ `iao:DirectiveInformationEntity`) | Prescribes the required function and technical constraints at the site |
| **Installed equipment** | `fl:Equipment` (⊑ `iof-core:MaterialArtifact`) | The transient physical item occupying the site during a bounded period |

Both identifiers (code and tag) **denote the functional location site**, not the equipment.  The relationship between a tag and the equipment currently at that position is a derived property chain (`fl:hasTag`), not a first-class assertion.

---

## Competency questions

| # | Question |
|---|---|
| CQ1 | What equipment is currently installed at the functional location identified by a given FL code? |
| CQ2 | What maintenance records and time-series datasets are anchored to the position identified by a given equipment tag, regardless of which equipment instance was installed at the time? |
| CQ3 | What functional locations are hierarchically under a given plant site at any depth? |
| CQ4 | Which functional locations have a specification that requires a gas-liquid separation function? |
| CQ5 | What equipment is currently installed within 10 m (Euclidean) of a given functional location? |
| CQ6 | For each piece of separation equipment, what functional location is it installed at, and what does the specification for that location require? |
| CQ7 | For a given functional location, retrieve in one query its organizational code, equipment tag, functional specification, currently installed equipment, and maintenance records — using the site as the integration key. |

------

## Citation

If you use this ontology, please cite the FOIS 2026 paper where the underlying ODP was originally proposed:

```bibtex
@inproceedings{santos2026functional,
  author    = {Santos, Nicolau and Antunes, Cau{\~a} and Rojas, Haroldo and
               Carbonera, Joel and Abel, Mara and Petry, Rafael and Romeu, Regis},
  title     = {An Ontology Design Pattern for Functional Locations in
               Industrial Asset Management},
  booktitle = {Proceedings of the 14th International Conference on Formal
               Ontology in Information Systems (FOIS 2026)},
  year      = {2026},
}
```
---

## License

[MIT](LICENSE) © 2025-2026 Nicolau Santos and contributors.

---

## Versions

### Stable release versions

The latest version of the ontology can always be found at:

https://www.inf.ufrgs.br/ontologies/ofl.owl

### Editors' version

Editors of this ontology should use the edit version, [src/ontology/ofl-edit.owl](src/ontology/ofl-edit.owl)

## Contact

Please use this GitHub repository's [Issue tracker](https://github.com/INF-UFRGS-Ontologies/OFL/issues) to request new terms/classes or report errors or specific concerns related to the ontology.

---

## Acknowledgements

Developed within the OntoKG project (Petrobras/ANP, SIGITEC 2025/00193-0).

This ontology repository was created using the [Ontology Development Kit (ODK)](https://github.com/INCATools/ontology-development-kit).
