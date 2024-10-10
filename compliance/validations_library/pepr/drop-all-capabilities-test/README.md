# README.md

**NAME** - check-new-pods-drop-all-capabilities-test

**INPUT** - Creates new pods from a specified manifest file and collects them. The manifest file is: https://repo1.dso.mil/big-bang/product/packages/kyverno-policies/-/raw/main/chart/tests/manifests/require-drop-all-capabilities.yaml.

**POLICY** - Checks if all newly created pods have dropped all capabilities in their security context.

**NOTES** - Hardcodes that the expected pods to be created are: require-drop-all-capabilities-1, require-drop-all-capabilities-2, require-drop-all-capabilities-3, require-drop-all-capabilities-4, require-drop-all-capabilities-5. All pods are created because Pepr mutates pods.