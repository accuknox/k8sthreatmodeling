# Threat Model for KubeArmor

[KubeArmor](https://github.com/kubearmor/kubearmor) is a k8s-native systems
security policy enforcement engine that enables to reduce the attack surface of
the application pods by restricting its systems operations. The restrictions
could be specified in the form of a) what processes the pod can spawn b) what
file system paths can it have access to c) what linux capabilities can the
containers in the pod use.

### Threat Model

<center><img src=./ka-threat-model.png></center>

Threat Model shows the modules involved in KubeArmor and the connectivity
involved. Also detailed out is the trust boundary at the Cluster, Node and
Internet level. This allows the Threat Modeling tool to decide what attacks
should be considered for KubeArmor as a system.

For full report, [check here](https://refined-github-html-preview.kidonng.workers.dev/accuknox/k8sthreatmodeling/raw/main/models/kubearmor/KubeArmor%20Threat%20Model.htm).
