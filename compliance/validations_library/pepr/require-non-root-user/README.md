# README.md

**NAME** - check-all-pods-require-non-root-user

**INPUT** - This validation collects all pods across all namespaces in the Kubernetes cluster.

**POLICY** - This policy checks if all pods require a non-root user. Specifically, it ensures that all containers within the pods have `runAsNonRoot` set to true and `runAsUser` set to a non-zero value. The policy also includes exemptions for certain namespaces, pods, and init containers.

**NOTES** - The exempted namespaces are: "uds-dev-stack", "zarf", "kube-system". The exempted pods are: "*/neuvector-controller-pod-*", "*/promtail-*". The exempted init container names are: "istio-init".