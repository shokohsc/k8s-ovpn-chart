# k8s-ovpn-chart

![Version: 0.1.2](https://img.shields.io/badge/Version-0.1.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.4](https://img.shields.io/badge/AppVersion-2.4-informational?style=flat-square)

Roll your own OpenVPN server

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| suda | admin@suda.pl |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | node/pod affinities (requires Kubernetes >=1.6) |
| automatic.cipher | string | `"AES-256-CBC"` | Cipher used |
| automatic.digestAlgorythm | string | `"SHA384"` | Authenticate  packets with HMAC using the given message digest algorithm (auth). |
| automatic.dnsServer | string | `"8.8.8.8"` | DNS Server IP |
| automatic.enabled | bool | `false` | Skip manual steps and generate configuration & pki according to values config, Warning, PKI will be passwordless ! |
| automatic.externalHostname | string | `""` | Hostname OR Ip of cluster openvpn entrypoint, default to 'domain.tld' so you must define it |
| automatic.externalPort | string | `""` | Port cluster openvpn entrypoint, defaults to service.port (nodePort) |
| automatic.extraOptions | list | `[]` | Additional options for openvpn configuration |
| automatic.persistence.accessModes | list | `["ReadWriteOnce"]` | PersistentVolumeClaim access modes |
| automatic.persistence.annotations | object | `{}` | PersistentVolumeClaim annotations |
| automatic.persistence.mountPath | string | `"/etc/openvpn"` | PersistentVolumeClaim mounting path |
| automatic.persistence.size | string | `"8Gi"` | PersistentVolumeClaim size request |
| fullnameOverride | string | `""` | release full release name override option |
| image.pullPolicy | string | `"IfNotPresent"` | container image pull policy |
| image.repository | string | `"kylemanna/openvpn"` | container image repository |
| image.tag | string | `""` | container image tag or Chart appVersion if undefined |
| limitTraficToNamespace | bool | `true` | limit network traffic just to OpenVPN namespace |
| limitedCidr | string | `"10.0.0.0/8"` | CIDR to be blocked out |
| nameOverride | string | `""` | release name override option |
| nodeSelector | object | `{}` | node labels for pod assignment |
| resources | object | `{}` | pod resource requests & limits |
| service.port | int | `31304` | OpenVPN port |
| service.protocol | string | `"TCP"` | OpenVPN protocol |
| service.type | string | `"NodePort"` | Service type |
| tolerations | list | `[]` | node taints to tolerate (requires Kubernetes >=1.6) |