DEPLOY TRAEFIK
==============
helm repo add traefik https://containous.github.io/traefik-helm-chart
helm repo update
helm install traefik traefik/traefik

DASHBOARD
=========
kubectl apply -f dashboard.yaml
add '127.0.0.1 traefik.localhost' to hosts file
test dashboard at http://traefik.localhost/dashboard/

UPGRADE
=======
helm upgrade traefik traefik/traefik --values values.yaml

ACME/LETSENCRYPT
================
kubectl create secret generic dnsimple --from-literal=dns-token=XXXXXXXXXXXXXXXXXX
