# Release SOP

This document keeps the paper-code release consistent with companion PAT repositories.

## Before Code Release

- Keep the README concise and paper-facing.
- Mark unavailable code, configs, results, and checkpoints as preparing for release.
- Avoid commands that imply missing files are already available.
- Keep dataset and checkpoint directories documented with placeholder README files.

## Code Release Checklist

- Add source files under `src/` or project-specific modules.
- Finalize `requirements.txt`.
- Add runnable configs under `configs/`.
- Add training, testing, and evaluation entry points.
- Add checkpoint links or files under `checkpoints/`.
- Replace placeholder result cells with final paper numbers.
- Add visual comparisons under `assets/`.
- Run quick-start commands from a clean environment before tagging a release.

## Versioning

Use a GitHub release tag when the code is ready:

```bash
git tag v1.0.0
git push origin v1.0.0
```

