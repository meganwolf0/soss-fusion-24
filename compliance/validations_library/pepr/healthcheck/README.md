# README.md

**NAME** - pepr-health-check

**INPUT** - This validation collects the deployments for the Pepr application, specifically the `pepr-uds-core` and `pepr-uds-core-watcher` deployments in the `pepr-system` namespace.

**POLICY** - This policy checks if the Pepr application deployments are healthy by ensuring that both the controller and watcher deployments are available and have sufficient replicas.

**NOTES** - Ensure that the `pepr-uds-core` and `pepr-uds-core-watcher` deployments exist in the `pepr-system` namespace. The policy checks for the availability and replica count of these deployments.