# README.md

**NAME** - check-all-pods-drop-all-capabilities

**INPUT** - Collects all pods in all namespaces.

**POLICY** - Checks if all pods have dropped all capabilities in their security context by checking the `securityContext.capabilities.drop` field is set to `ALL`.

**NOTES** - Exemptions include namespaces: kube-system, istio-system, uds-dev-stack, zarf and pods: neuvector-controller-pod-*, neuvector-enforcer-pod-*.