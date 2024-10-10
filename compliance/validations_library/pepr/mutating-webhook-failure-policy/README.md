# README.md

**NAME** - pepr-mutating-webhook-failure-policy

**INPUT** - This validation collects the mutating webhook configurations in the Kubernetes cluster.

**POLICY** - This policy checks if the failure policy for the `pepr-uds-core` mutating webhook is set to "Fail".

**NOTES** - Ensure that the `pepr-uds-core` mutating webhook configuration exists in the cluster. The policy checks the `failurePolicy` field of the webhook configuration.