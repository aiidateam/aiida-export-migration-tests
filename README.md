# Testing of AiiDA export file migrations

Test modules for migration of [AiiDA](http://www.aiida.net) export files.

Can be installed by adding `testing` package, when installing AiiDA:

```shell
pip install aiida[testing]
```

## Q&A

**Q: Why not include these tests in the core of AiiDA?**  
**A:** These tests demand fixed AiiDA export files.
In order to not take up unneccesary disk space, when installing AiiDA,
these tests have been separated out of [aiida-core](https://github.com/aiidateam/aiida_core).
Furthermore, the legacy export versions will never change,
i.e. the incremental migration functions need only be thoroughly tested once,
and will therefore not be affected by changes to the core of the AiiDA code in any way.

**Q: What happens when the export version is upped?**  
**A:** A new export file will be added to this repo as well as a new test-filled file.

**Q: What if the import system changes in AiiDA core?**  
**A:** Tests relying on importing exported files into the AiiDA database
will still be found in [aiida-core](https://github.com/aiidateam/aiida_core).
This repo is only for testing the incremental migration functions for different export versions.
