# SBOM Bridging Ontology for Mapping

A SKOS bridge vocabulary and SSSOM crosswalk files for
Software Bill of Materials (SBOM) minimum-element standards.

## What this is

Different organisations (BSI, CISA, G7, NTIA) publish their own lists of
minimum elements that an SBOM shall or should contain.
Different SBOM data exchange (CycloneDX, SPDX) and serialisation formats have
their own field names.
This project provides a neutral bridge vocabulary that connects the two.

**`docs/sbom.ttl`** -- a small [SKOS] ontology that assigns stable,
persistent IRIs to each minimum-element concept.

**`docs/req/*`** -- ontologies that assign persistent IRIs
to each minimum element in an information requirement specification.
These IRIs are required as a source in a mapping.
(For target, we don't need this since the SBOM data exchange formats are
fortunately already have persistent IRIs).

**`docs/mapping/*.sssom.tsv`** -- [SSSOM] mapping files that record how each
minimum-element concept maps to a field in a target format, with the shared
bridge concept cited in the `see_also` column.

[SKOS]: https://www.w3.org/TR/skos-reference/
[SSSOM]: https://mapping-commons.github.io/sssom/dev/

## Information requirement specifications

| File | Specification | Namespace |
| ---- | ------------- | --------- |
| `docs/req/g7ai/g7ai.ttl` | G7 SBOM for AI - Minimum Elements (2026) | `g7ai` |
| `docs/req/ntia/ntia/ttl` | NTIA SBOM Minimum Elements (2021) | `ntia` |

## Mappings

| File | Source | Target |
| ---- | ------ | ------ |
| `docs/mapping/g7ai-spdx31.sssom.tsv` | G7 SBOM for AI - Minimum Elements | SPDX 3.1-dev |
| `docs/mapping/ntia-spdx31.sssom.tsv` | NTIA SBOM Minimum Elements | SPDX 3.1-dev |

## Namespace

Base IRI: `https://w3id.org/sbom/` (registration pending).

## License

[CC-BY-4.0](LICENSE)
