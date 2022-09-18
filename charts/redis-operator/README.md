# Redis operator - helm chart

## Configuration

The following table lists the configurable parameters of the redis-operator chart and their default values.

| Parameter                    | Description                                                | Default                  |
| ---------------------------- | ---------------------------------------------------------- | -------------------------|
| `replicaCount`               | Redis Operator pod replicas                                | `1`                      |
| `image.repository`           | Redis Operator image repository                            | `bringg/redis-operator`  |
| `image.tag`                  | Redis Operator image tag (immutable tags are recommended)  | `""`                     |
| `image.pullPolicy`           | Redis Operator image pull policy                           | `IfNotPresent`           |
| `imagePullSecrets`           | The list of image pull secrets for Redis Operator image    | `[]`                     |
| `nameOverride`               | String to partially override `redis-operator.fullname`     | `""`                     |
| `fullnameOverride`           | String to fully override `redis-operator.fullname`         | `""`                     |
| `serviceAccount.annotations` | Extra annotations to be added to the ServiceAccount        | `{}`                     |
| `serviceAccount.name`        | The name of the ServiceAccount to use.                     | `""`                     |
| `podAnnotations`             | Annotations for Redis Operator pods                        | `{}`                     |
| `podSecurityContext`         | Provide `.spec.securityContext` for the Redis Operator pod | `{"runasNonRoot": true}` |
| `resources`                  | Provide resource limits for the Redis Operator container   | `{}`                     |
| `logLevel`                   | Set log level for Redis Operator process                   | `info`                   |
| `extraOperatorArgs`          | Extra arguments for Redis Operator command                 | `[]`                     |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

**For example:**

```bash
# first make sure the operator repo is added
helm repo add redis-operator https://bringg.github.io/redis-operator

# override image.tag
helm install redis-operator --set image.tag="v0.3.0"
```
