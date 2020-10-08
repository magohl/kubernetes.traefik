helm repo add traefik https://containous.github.io/traefik-helm-chart
helm repo update
helm install traefik traefik/traefik

kubectl apply -f dashboard.yaml

#add 127.0.0.1 traefik.localhost    -> hosts

test dashboard at http://traefik.localhost/dashboard/