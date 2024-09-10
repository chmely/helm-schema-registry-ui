# helm-schema-registry-ui
This is a Helm chart for landoop/schema-registry-ui for local Docker Desktop Kubernetes cluster.

To deploy the helm chart:
```
helm upgrade --install schema-registry-ui oci://registry-1.docker.io/chmely/schema-registry-ui --namespace infra
```

These are the defaults that can be configured:
```
service:
  port: 8088
  type: ClusterIP

ingress:
  enabled: true
  host: schema-registry-ui.kubernetes.docker.internal
  tlsSecretName: tls

env:
  - name: SCHEMAREGISTRY_URL
    value: "http://confluentinc-schema-registry:8081"
  - name: PROXY
    value: "true"
  - name: ALLOW_GLOBAL
    value: "1"
  - name: ALLOW_TRANSITIVE
    value: "1"
  - name: ALLOW_DELETION
    value: "1"
```
