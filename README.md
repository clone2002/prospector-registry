# Prospector registry

The shared job-board registry read by every Prospector install at launch: companies, their applicant-tracking-system job boards (Ashby, Greenhouse, Lever, Workday), board status, and industry tags. Company facts only; nothing about any person or any install is ever in this file.

Files:
- `registry.json`: the published registry (schema version 3). `_meta.registry_version` is a monotonic integer; installs apply a download only when it is newer than their copy and the checksum matches.
- `registry.json.sha256`: SHA-256 of `registry.json`.

Maintained from the Prospector repo's registry scripts. Data license: Open Database License (ODbL) v1.0, see LICENSE; credit "Prospector registry, github.com/clone2002/prospector-registry" and share adapted databases under the same terms.
