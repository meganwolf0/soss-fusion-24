# SOSS Fusion 2024 Demo

This is a demo repo for the SOSS Fusion 2024 presentation titled "Validating Validations - Who's Watching the Watcher?"

## Prerequisites
* [Lula](https://docs.lula.dev/getting-started/)
* [k3d](https://k3d.io/v5.7.4/#releases)
* [UDS CLI]() -> Running [UDS-Core]()
    ```
    uds deploy k3d-core-demo:<version>
    ```

## Content
* compliance - Demo OSCAL compliance documentation for the UDS system + validations
* testfiles - Kubernetes manifests for testing compliance flux

## Demos

Trying to answer the question - Is the controller's operations in the system system continually working as expected?
(i.e., "is the outcome still what I expect it to be")

### Evaluation of Controller behavior in evolving system

Demonstrate evaluation of controller behavior by testing validation and mutation. (system that becomes too permissive - want a flag on evaluation)

Run the following:

1. Just non-executable validations `lula validate -f compliance/component.yaml -t read`  -> passes
2. Executable validations `lula validate -f compliance/component.yaml -t write`  -> passes
3. Add an exemption `kubectl apply -f testfiles/exemption.yaml` (e.g., add one for a namespace that a validation pod is being created in)
4. Run (1) again -> passes (limitations of read-only) -> `lula evaluate -f compliance/assessment-results.yaml -t read` (pass!)
5. Run (2) again -> fails -> `lula evaluate -f compliance/assessment-results.yaml -t write` (fail - system changed!)

### Test a Controller's CR response

Demonstrate that a controller responds to the CRD with the expected resource creation in the cluster

1. Execute the component.yaml validate with `lula validate -f compliance/component.yaml -t controller-check` -> passes
2. (Optional) Apply the netpol-manifests + webhook to block network policies from being created
3. Run (1) again -> fails
