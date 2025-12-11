# Container

## Configuration Parameters

| UI Name | Key (Code) | Description |
| :--- | :--- | :--- |
| **Name** | `name` | Provide Stage name. |
| **Image link** | `image` | Docker image path. Examples: mysql, mysql:latest, bitnami/argo-cd:2.1.2, localhost:5000/bitnami/argo-cd:2.1.2, registry.redhat.io/rhel7:latest. |
| **Image pull policy** | `imagePullPolicy` | Defines when the image will be pulled(downloaded). Possible values:<br><br>If not present - download only if not exist locally;<br><br>Always - download before each start;<br><br>Never - do not download use only local copy. |
| **Requests CPU** | `requestsCpu` | Minimal number of CPU cores reserved for this container. |
| **Requests memory** | `requestsMemory` | Minimal amount of RAM reserved for this container. |
| **Limits CPU** | `limitsCpu` | Maximum limit of CPU cores that container can use. |
| **Limits memory** | `limitsMemory` | Maximum limit of RAM that container can use. |
| **Mount project params** | `mountProjectParams` | Defines whether to mount all project params as environment variables inside the Pod. |
| **Authentication type** | `imagePullSecretType` |  Authentication mode that could be one of these:<br><br>1) Not applicable - image pull secrets are not needed, as the image is pulled from the public registry;<br><br>2) New - create a new image pull secret on the fly by providing all necessary information (see below);<br><br>3) Provided - use existing image pull secret by providing it's name (Image pull secret name). |
| **Image pull secret name** | `imagePullSecretName` | Name of the secret to pull the image. Note that it must exist within the same k8s namespace as the current pipeline. |
| **Username** | `username` | User name for registry authentication. |
| **Password** | `password` | Password for registry authentication. |
| **Registry** | `registry` | Name of the registry for authentication. |
| **Command** | `command` | Command that will be executed once Pod is be created. |

