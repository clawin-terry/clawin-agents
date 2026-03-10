# Third-Party and Embedded Content Notice

This repository publishes **Clawin public output packages**.

## Repository-level license

Unless a subdirectory or embedded component states otherwise, the original Clawin-authored catalog files in this repository are published under the Apache License 2.0.

That includes repository-level materials such as:
- `README.md`
- `INSTALL.md`
- `CATALOG.md`
- `CONTRIBUTING.md`
- `docs/shareable-folder-package.md`
- Clawin-authored packaging metadata and folder structure decisions

## Embedded skills and third-party materials

Some published agent packages include bundled skills or embedded third-party materials under paths such as:

```text
categories/.../workspace/skills/
```

Those embedded components may include their own:
- license files
- upstream notices
- origin metadata
- usage terms

Examples in this repository include materials with their own license or origin metadata under bundled skill folders.

## Rule of interpretation

If a bundled component contains its own license or explicit upstream metadata, that component should be treated according to its own terms.
The top-level Apache License should not be interpreted as replacing a more specific license or notice shipped inside a bundled component.

## Practical guidance

If you reuse or redistribute content from this repository:
1. check the top-level `LICENSE`
2. check the specific package you are copying
3. check any bundled skill under `workspace/skills/` for its own license or origin metadata
4. preserve any required notices when redistributing modified or repackaged outputs
