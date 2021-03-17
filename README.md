# OpenShift_Descheduler

Descheduling involves evicting pods based on specific policies so that the pods can be rescheduled onto more appropriate nodes.

Your cluster can benefit from descheduling and rescheduling already-running pods for various reasons:

Nodes are under- or over-utilized.

- Pod and node affinity requirements, such as taints or labels, have changed and the original scheduling decisions are no longer appropriate for certain nodes.

- Node failure requires pods to be moved.

- New nodes are added to clusters.

## Steps:
- oc create -f rbac.yaml

- oc create configmap descheduler-policy-configmap -n kube-system --from-file=policy.yaml

- oc create -f descheduler-job.yaml -n kube-system

