# homelab
Repository for all things homelab

## Kubernetes Setup
- Install flux CLI and run precheck `flux check --pre`
```
curl -o /tmp/flux.tar.gz -sLO https://github.com/fluxcd/flux2/releases/download/v2.6.4/flux_2.6.4_linux_amd64.tar.gz
tar -C /tmp/ -zxvf /tmp/flux.tar.gz
mv /tmp/flux /usr/local/bin/flux
chmod +x /usr/local/bin/flux

flux-check --pre
```
- Setup flux and reconcile it with this repo
```
flux bootstrap github \
  --token-auth=false \
  --owner=lucashicks1 \
  --repository=homelab \
  --read-write-key \
  --path=k8s/clusters/dev \
  --personal \
  --components-extra=image-reflector-controller,image-automation-controller \
  --branch main
  ```
- Create a bitwarden secret for bitwarden to use
```
kubectl create secret generic bw-auth-token -n <NAMESPACE> --from-literal=token="<SECRET>"
```