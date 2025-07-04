# cloudflare-tunnel

![Version: 0.5.11](https://img.shields.io/badge/Version-0.5.11-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2025.5.0](https://img.shields.io/badge/AppVersion-2025.5.0-informational?style=flat-square)

Creation of a cloudflared deployment - a reverse tunnel for an environment

**Homepage:** <https://github.com/lexfrei/charts/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Aleksei Sviridkin | <f@lex.la> | <https://me.lex.la> |

## Source Code

* <https://github.com/lexfrei/charts/>
* <https://github.com/cloudflare/cloudflared/>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Default affinity is to spread out over nodes; use this to override |
| cloudflare | object | `{"account":"","enableDefault404":true,"enableWarp":false,"ingress":[],"secret":"","secretName":null,"tunnelId":"","tunnelName":""}` | Cloudflare parameters |
| cloudflare.account | string | `""` | Your Cloudflare account number |
| cloudflare.enableDefault404 | bool | `true` | If true, enable the default 404 page. Needs to be false if you want to use a '*' wildcard rule. |
| cloudflare.enableWarp | bool | `false` | If true, turn on WARP routing for TCP |
| cloudflare.ingress | list | `[]` | Define ingress rules for the tunnel See https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/configuration/configuration-file/ingress |
| cloudflare.secret | string | `""` | The secret for the tunnel |
| cloudflare.secretName | string | `nil` | If defined, no secret is created for the credentials, and instead, the secret referenced is used |
| cloudflare.tunnelId | string | `""` | The ID of the above tunnel |
| cloudflare.tunnelName | string | `""` | The name of the tunnel this instance will serve |
| fullnameOverride | string | `""` |  |
| image | object | `{"pullPolicy":"IfNotPresent","repository":"cloudflare/cloudflared","tag":""}` | The image to use |
| image.tag | string | `""` | If supplied, this overrides "appVersion" |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{"runAsNonRoot":true,"runAsUser":65532}` | Security items common to everything in the pod.  Here we require that it does not run as the user defined in the image, literally named "nonroot" |
| replicaCount | int | `2` | The version of the image to use |
| resources | object | `{}` |  |
| securityContext | object | `{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"readOnlyRootFilesystem":true}` | Security items for one container. We lock it down |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.name | string | `""` | The name of the service account to use If not set and create is true, a name is generated using the fullname template |
| serviceMonitor.enabled | bool | `false` | Enable prometheus Service Monitor |
| tolerations | list | `[]` |  |
