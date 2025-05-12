# Keda core
- https://keda.sh/docs/2.17/deploy/#installing
- https://keda.sh/docs/2.17/deploy/
## helm repo add kedacore https://kedacore.github.io/charts  
## helm repo update
## helm install keda kedacore/keda --namespace keda --create-namespace

# keda-crds
$ kubectl apply --server-side -f keda-2.17.0-crds.yaml --namespace keda
customresourcedefinition.apiextensions.k8s.io/cloudeventsources.eventing.keda.sh serverside-applied
customresourcedefinition.apiextensions.k8s.io/clustercloudeventsources.eventing.keda.sh serverside-applied
customresourcedefinition.apiextensions.k8s.io/clustertriggerauthentications.keda.sh serverside-applied
customresourcedefinition.apiextensions.k8s.io/scaledjobs.keda.sh serverside-applied
customresourcedefinition.apiextensions.k8s.io/scaledobjects.keda.sh serverside-applied
customresourcedefinition.apiextensions.k8s.io/triggerauthentications.keda.sh serverside-applied

#  Including admission webhooks
kubectl apply --server-side -f https://github.com/kedacore/keda/releases/download/v2.17.0/keda-2.17.0.yaml
# Without admission webhooks
kubectl apply --server-side -f https://github.com/kedacore/keda/releases/download/v2.17.0/keda-2.17.0-core.yaml
Alternatively you can download the file and deploy it from the local path:

# Including admission webhooks
kubectl apply --server-side -f keda-2.17.0.yaml
# Without admission webhooks
kubectl apply --server-side -f keda-2.17.0-core.yaml
