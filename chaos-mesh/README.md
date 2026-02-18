# Install
sh chaos-mesh-install.sh

# Expose Dashboard via LB
kubectl expose service -n chaos-mesh chaos-dashboard --type=LoadBalancer --name=http --target-port=2333 --port=30010 --name=chaos-dash-ext

# Chaos Dashboard
# https://chaos-mesh.org/docs/simulate-heavy-stress-on-kubernetes/
http://127.0.0.1:30010/#/dashboard
