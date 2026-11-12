# Prospector registry

The shared job-board registry read by every Prospector install at launch: companies, their applicant-tracking-system job boards (Ashby, Greenhouse, Lever, Workday), board status, and industry tags. Company facts only; nothing about any person or any install is ever in this file.

Files:
- `registry.json`: the published registry (schema version 3). `_meta.registry_version` is a monotonic integer; installs apply a download only when it is newer than their copy and the checksum matches.
- `registry.json.sha256`: SHA-256 of `registry.json`.
- `icons.json`: company icons, one small PNG (at most 32 pixels on each side, base64) per alive company whose icon was read, by company id, read from each company's own website. `_meta.version` is a monotonic integer that goes up by one only at a publish whose icons differ from the last published ones (an icon added, changed, or dropped) or whose file text otherwise changed (its notice or its layout); `registry.json`'s `_meta.icons` names the version, the SHA-256 of this file, the count, and the size, so a reader can fetch it only when that version is newer than its copy and check it against that hash.

Maintained from the Prospector repo's registry scripts. Data license: Open Database License (ODbL) v1.0, see LICENSE; credit "Prospector registry, github.com/clone2002/prospector-registry" and share adapted databases under the same terms.

Icons: each icon in `icons.json` is the mark of the company its id names, read from that company's own website and kept here only to identify the company beside its name. Each mark belongs to its owner. The icons are not part of the registry database and are outside the Open Database License grant above; see LICENSE.
