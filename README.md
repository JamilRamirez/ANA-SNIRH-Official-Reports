# ANA/SNIRH Official Reports Archive

Preserved copies of hydrometeorological XLSX reports published through Peru's Autoridad Nacional del Agua (ANA) and its Sistema Nacional de Informacion de Recursos Hidricos (SNIRH).

This is an independent archive maintained for reproducible access by [ANA-SNIRH Spatial Station Finder](https://jamilramirez.shinyapps.io/ANA_SNIRH_WEB/). It is not an official ANA repository, and the files are not modified or reissued by this project.

## Repository contents

Reports are organized by hydrographic unit and identified by the ANA/SNIRH `IDConfig`:

```text
<CodigoUH>_<basin>/
└── _raw_reportes_xlsx/
    └── IDConfig_<id>_completo.xlsx
```

Root metadata:

- `inventory.csv`: one row per archived report, including its `IDConfig`, hydrographic unit, relative path, and file size. Publications produced by newer pipeline runs may also include an MD5 checksum.
- `publication_summary.csv`: compact publication totals.
- `data_snapshot.csv`: source cutoff and publication metadata when supplied by the current pipeline release.

The inventory is the authoritative index for resolving a report path. Folder names are descriptive and should not be parsed as stable identifiers.

## Direct access

A file listed in `inventory.csv` can be downloaded from GitHub using its `ruta_relativa` value:

```text
https://raw.githubusercontent.com/JamilRamirez/ANA-SNIRH-Official-Reports/main/<ruta_relativa>
```

Use the [official ANA/SNIRH basin viewer](https://snirh.ana.gob.pe/VisorPorCuenca/) to check the most recent source information or records published after this archive's indicated cutoff.

## Provenance and integrity

The companion update pipeline retrieves the ANA/SNIRH reports, verifies the publication set, and replaces this public mirror during a release. The application uses the inventory to link a validated `IDConfig` to its preserved report.

These XLSX files are source records. Normalized long-format series derived from them are published separately in [ANA-SNIRH-Normalized-Series](https://github.com/JamilRamirez/ANA-SNIRH-Normalized-Series).

## Data rights and attribution

ANA/SNIRH is the source publisher of the original observations and reports. No repository-wide software or open-data license is asserted here for those third-party files. Access to a file does not by itself grant permission to relicense it; users should verify ANA's current terms and provide appropriate source attribution for their intended use.

## Update policy

The archive is intended to be refreshed monthly. During publication, indexed XLSX files and generated metadata are replaced by the verified output of the update pipeline.

Maintained by [Jamil Ramirez](https://jamilramirez.github.io/).
