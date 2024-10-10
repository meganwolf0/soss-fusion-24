# README.md

**NAME** - check-new-pods-disallow-root-user-test

**INPUT** - This validation creates a new resource from the file `https://repo1.dso.mil/big-bang/product/packages/kyverno-policies/-/raw/main/chart/tests/manifests/require-non-root-user.yaml`.

**POLICY** - This policy checks if only the allowed pods were created and if all mutated pods have a security context.

**NOTES** - The allowed pods names are: "require-non-root-user-9" to "require-non-root-user-14" and "require-non-root-user-1" to "require-non-root-user-2".
