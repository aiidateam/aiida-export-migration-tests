# Testing of AiiDA export file migrations

Test modules for migration of [AiiDA](http://www.aiida.net) export files.

Can be installed by adding `testing` package, when installing AiiDA:

```shell
pip install aiida-core[testing]
```

> **Note**: This only works for AiiDA *v1.0.0* and newer.

Historical table of version comparisons between releases of this module and AiiDA, including when tests for the different export versions are first included.

| This module | AiiDA | Export versions (when first included) |
| ----------- | ----- | ------------------------------------- |
| [0.9.0](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.9.0) | to be released | 0.9 |
| [0.8.0](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.8.0) | [1.0.1](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.1) | 0.8 |
| [0.7.0](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.7.0) | [1.0.0b4](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.0b4) | 0.6, 0.7 |
| 0.6.0 | [1.0.0b4](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.0b4) | |
| [0.5.2](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.5.2) | [1.0.0b3](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.0b3) | |
| [0.5.1](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.5.1) | [1.0.0b3](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.0b3) | |
| [0.5.0](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.5.0) | [1.0.0b3](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.0b3) | 0.4 -> 0.5 |
| [0.1.1](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.1.1) | [1.0.0b2](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.0b2) | |
| [0.1.0](https://github.com/aiidateam/aiida-export-migration-tests/releases/tag/v0.1.0) | [1.0.0b2](https://github.com/aiidateam/aiida-core/releases/tag/v1.0.0b2) | 0.1 -> 0.2 ; 0.2 -> 0.3 ; 0.3 -> 0.4 |

## Q&A

**Q: Why not include these test archives in the core of AiiDA?**  
**A:** In order to not take up unneccesary disk space, when installing AiiDA, these test archives have been separated out of [aiida-core](https://github.com/aiidateam/aiida-core).
Furthermore, the legacy export versions will never change, i.e., the incremental migration functions need only be thoroughly tested once, and will therefore not be affected by changes to the core of the AiiDA code in any way.

**Q: What happens when the export version is upped?**  
**A:** A new export archive file will be added to this repo as well as a new test-filled file (to [aiida-core](https://github.com/aiidateam/aiida-core) under `tests.tools.importexport.migration.`).

**Q: What if the import system changes in AiiDA core?**  
**A:** This repo is only for storing the export archives and their creation workflows for different export versions.
All tests can be found in [aiida-core](https://github.com/aiidateam/aiida-core).

## Release notes

### 0.9.0 (April 2020)

**AiiDA version**: _To be released_

Update repository with export archive for export version 0.9.
The file follows the naming of previous export version files having the suffix `_manual`, since it was not produced properly, i.e., through a new workflow run in AiiDA.
Instead, the export file `export_v0.8_manual.aiida` has been the unpacked, updated manually, and repacked.
This means the latest "proper" export file is `export_v0.4.aiida`.

Changes are expected to be released with AiiDA version 1.2.0.

*New file*: `export_v0.9_manual.aiida`

### 0.8.0 (November 2019)

**AiiDA version**: _1.0.0_

Update repository with export archive for export version 0.8.
The file follows the naming of previous export version files having the suffix `_manual`, since it was not produced properly, i.e., through a new workflow run in AiiDA.
Instead, the export file `export_v0.7_manual.aiida` has been the unpacked, updated manually, and repacked.
This means the latest "proper" export file is `export_v0.4.aiida`.

Changes are expected to be released with AiiDA version 1.0.1.

*New file*: `export_v0.8_manual.aiida`

### 0.7.0 (July 2019)

**AiiDA version**: _1.0.0b4_

Update repository with export archive for export versions 0.6 and 0.7.  
These files are named differently, having the suffix `_manual`, since they were not produced properly, i.e., through a new workflow run in AiiDA.
Instead, the export file `export_v0.4.aiida` has been the unpacked, updated manually, and repacked.

The file `export_v0.5.aiida` has also been made this way, and will therefore have its name changed accordingly.

*New files*:

- `export_v0.5_manual.aiida` (only the filename has been altered)
- `export_v0.6_manual.aiida`
- `export_v0.7_manual.aiida`

### 0.6.0 (July 2019)

**AiiDA version**: _1.0.0b4_

This version was never released.

### 0.5.2 (June 2019)

**AiiDA version**: _1.0.0b3_

Remove test files according to issue [#6](https://github.com/aiidateam/aiida-export-migration-tests/issues/6).
The files have been moved to [aiida-core](https://github.com/aiidateam/aiida-core) under `aiida.backends.tests.tools.importexport.migration.`.
As explained in the issue, the problem of having tests that concern files in [aiida-core](https://github.com/aiidateam/aiida-core), is that they cannot be skipped with a helpful message using `unittest.skip(<message>)`.

This repository has now become the keeper of the export archives and the workflows that created them.
Hence, it should only ever be touched, when a new export version is introduced in AiiDA, and a new archive must be added.

### 0.5.1 (June 2019)

**AiiDA version**: _1.0.0b3_

Update imports from aiida-core in accordance with the restructuring of the import/export-module.
For a reference, this was done in aiida-core PR [#3052](https://github.com/aiidateam/aiida-core/pull/3052).

### 0.5.0 (June 2019)

**AiiDA version**: _1.0.0b3_

Update version number of this repository to reflect the current `EXPORT_VERSION` in `aiida-core`.  
The version number is now as follows: `<EXPORT_VERSION>.<patch>`

Implement initial change related to the update of `EXPORT_VERSION` from 0.4 to 0.5:

- _Migration [0034](https://github.com/aiidateam/aiida-core/blob/b8eaffca3c448d1242eded845aa118b4bc1ae1a9/aiida/backends/djsite/db/migrations/0034_drop_node_columns_nodeversion_public.py)_: Remove fields/columns `"nodeversion"` and `"public"` from the `DbNode` model.
- _Migration [0036](https://github.com/aiidateam/aiida-core/blob/af56391b5bdfbbc3e1d0ef7d36180128bb28f695/aiida/backends/djsite/db/migrations/0036_drop_computer_transport_params.py)_: Remove field/column `"transport_params"` from the `DbComputer` model.

_Note_: The newly created `export_v0.5.aiida` under `/aiida-export-migration-tests/archives` is _not_ actually created from an AiiDA workflow, but instead a migration of `export_v0.4.aiida`.
This is because the changes between the versions are insignificant for the outcome of the workflow, and that only very minor changes have occurred.

### 0.1.1 (May 2019)

**AiiDA version**: _1.0.0b2_

Minor fixes due to changes in [aiida-core](https://github.com/aiidateam/aiida-core).

Folder `fixtures` changes name to `archives` to match the same change happening for aiida-core.  
The simple AiiDA export archives in aiida-core representing the different export versions have changed names:

- `export_v0.1_no_UPF.aiida` -> `export_v0.1_simple.aiida`
- `export_v0.2_no_UPF.aiida` -> `export_v0.2_simple.aiida`
- `export_v0.3_no_UPF.aiida` -> `export_v0.3_simple.aiida`
- `export_v0.4_no_UPF.aiida` -> `export_v0.4_simple.aiida`

A change in the conversion message included in `metadata.json` files, when a migration has been successfully performed, introduces the version of AiiDA into the message. In order to have the tests be version-agnostic, the `conversion_info` key has to be handled specially in the relevant tests.  
When migrating an archive, it is asserted that the correct conversion message appears in the migrated archive, and the `conversion_info` item is then popped from both the migrated archive and the archive imported for comparison.

### 0.1.0 (April 2019)

**AiiDA version**: _1.0.0b2_

First release.

Tests for step-wise export migrations from versions 0.1, 0.2, and 0.3.  
Representative export files created in specialized [Quantum Mobile](https://materialscloud.org/work/quantum-mobile) virtual machines by @yakutovicha to test currently known migrations from the basis of what could be exported at the time of the different export versions.

Table of version comparisons (similar to the one in [aiida-core](https://github.com/aiidateam/aiida-core) PR [#2478](https://github.com/aiidateam/aiida-core/pull/2478)).

| Export version | AiiDA version | AiiDA version release date | Found changed in commit |
| -------------- | ------------- | -------------------------- | ----------------------- |
| ~~v0.1~~* | ~~0.6.0.1~~ | ~~01.03.2016~~ | ~~as exported by 0.6.0~~ |
| v0.2 | 0.9.1 | 01.09.2017 | [189e29fea4c7f4213d0be0914d55cccaa581c364](https://github.com/aiidateam/aiida-core/commit/189e29fea4c7f4213d0be0914d55cccaa581c364) (v0.7.0) |
| v0.3 | 0.12.3 | 04.03.2019 | [788d3206e0eaaf062d1a13710aaa64a18a0bbbcd](https://github.com/aiidateam/aiida-core/commit/788d3206e0eaaf062d1a13710aaa64a18a0bbbcd) (v0.10.0rc1) |
| v0.4 | 1.0.0b2 | 09.04.2019 | [1673ec28e8b594693a0ee4cdec82669e72abcc4c](https://github.com/aiidateam/aiida-core/commit/1673ec28e8b594693a0ee4cdec82669e72abcc4c) (v1.0.0b1) |

\*Due to the following reasons, we decided **not** to invest an effort in making the representative archive migration for 0.1:

1. The earliest version released on PyPi is 0.8.0rc1 (22.03.2017).
1. The previous stable version (AiiDA 0.5.0) was not working in a virtual environment.
1. The migration from v0.1 to v0.2 is small and quite simple.
   If an export file should be found that cannot be properly migrated, due to this step, it can be migrated manually with little effort.

## Representative export files creation

To create the representative export files, a simple workflow was developed by @yakutovicha that runs two consequtive [QuantumESPRESSO](https://www.quantum-espresso.org) PW calculations.
First an SCF calculation, followed by an MD calculation.

The workflows can be found in the repository's folder `.qm`, and correspond to the following export versions and [Quantum Mobile](https://github.com/marvel-nccr/quantum-mobile/releases/) editions:

| Export version | Workflow | Run workflow script | Quantum Mobile |
| -------------- | -------- | ------------------- | -------------- |
| ~~v0.1~~* | - | - | - |
| v0.2 | [wf.py](aiida-export-migration-tests/.qm/wf.py) | [run_wf.py](aiida-export-migration-tests/.qm/run_wf.py) | [historical_aiida_0.9.1](https://github.com/marvel-nccr/quantum-mobile/tree/historical_aiida_0.9.1) |
| v0.3 | [wf.py](aiida-export-migration-tests/.qm/wf.py) | [run_wf.py](aiida-export-migration-tests/.qm/run_wf.py) | [v19.03.0](https://github.com/marvel-nccr/quantum-mobile/releases/tag/19.03.0) |
| v0.4 | [wf_aiida_1_0.py](aiida-export-migration-tests/.qm/wf_aiida_1_0.py) | [run_wf_aiida_1_0.py](aiida-export-migration-tests/.qm/run_wf_aiida_1_0.py) | _in development_ |

\*See section _Release notes#0.1.0 (April 2019)_.

They contain the following AiiDA node types (according to AiiDA **1.0.0**):

| Node type | Parent-type tree, up to `Node` |
| --------- | -------- |
| Float | NumericType -> BaseType/Data -> Node |
| Int | NumericType -> BaseType/Data -> Node |
| Dict | Data -> Node |
| FolderData | Data -> Node |
| RemoteData | Data -> Node |
| StructureData | Data -> Node |
| UpfData | SinglefileData -> Data -> Node |
| KpointsData | ArrayData -> Data -> Node |
| BandsData | KpointsData -> ArrayData -> Data -> Node |
| TrajectoryData | ArrayData -> Data -> Node |
| Code | Data -> Node |
| WorkChainNode | WorkflowNode -> ProcessNode -> Node |
| CalcJobNode | CalculationNode -> ProcessNode -> Node |
