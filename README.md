# SBOM Bridging Ontology for Mapping

A SKOS bridge vocabulary and SSSOM crosswalk files for
Software Bill of Materials (SBOM) minimum-element standards.

## What this is

1) Different organisations (BSI, CISA, G7, NTIA) publish their own lists of
   minimum elements that an SBOM shall or should contain.
2) Different SBOM data exchange (CycloneDX, SPDX) and serialisation formats have
   their own field names.
3) This project provides a neutral bridge vocabulary that connects (1) and (2).

**`docs/sbom.ttl`** -- a small [SKOS] ontology that assigns stable,
persistent IRIs to each minimum-element concept. It has two layers:

- a *bridge concept scheme* (`sbom:bridge`) that abstracts across all source standards
- per-standard concept schemes whose concepts link to bridge concepts
  via `skos:exactMatch` / `skos:closeMatch`

**`docs/mapping/*.sssom.tsv`** -- [SSSOM] mapping files that record how each
minimum-element concept maps to a field in a target format, with the shared
bridge concept cited in the `see_also` column.

[SKOS]: https://www.w3.org/TR/skos-reference/
[SSSOM]: https://mapping-commons.github.io/sssom/dev/

## Covered standards

| Prefix | Standard |
| ------ | -------- |
| `ntia:` | NTIA SBOM Minimum Elements (2021) |
| `g7ai:` | G7 SBOM for AI - Minimum Elements (2026) |

## Completed mappings

| File | Source | Target |
| ---- | ------ | ------ |
| `docs/mapping/g7ai-spdx31.sssom.tsv` | G7 SBOM for AI - Minimum Elements | SPDX 3.1-dev |
| `docs/mapping/ntia-spdx31.sssom.tsv` | NTIA SBOM Minimum Elements | SPDX 3.1-dev |

## Namespace

Base IRI: `https://w3id.org/sbom/`  
Persistent redirects via [w3id.org](https://w3id.org) (registration pending).

## License

[CC-BY-4.0](LICENSE)
