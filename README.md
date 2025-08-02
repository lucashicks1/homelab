# homelab
Repository for all things homelab

flux create source helm bitwarden --url https://charts.bitwarden.com --namespace bitwarden --export > ./k8s/clusters/dev/bitwarden-source.yaml

flux create helmrelease bitwarden --chart sm-operator \
  --source HelmRepository/bitwarden \
  --namespace bitwarden \
  --export > ./k8s/clusters/dev/bitwarden-helmrelease.yaml