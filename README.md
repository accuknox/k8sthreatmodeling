# K8s Threat Modeling

Threat Modeling allows one to specify the components of the software stack or a
deployment and specify the trust boundaries. The output of a Threat modeling
activity is a list of possible attacks on the system/deployment. The team can
then evaluate each of the possible attacks and provide a mitigation or
investigation strategy.

TLDR;
* [Sample Threat Report for KubeArmor](./models/kubearmor/README.md)
* [Threat Modeling - Step-by-Step Guide](./howto-threatmodeling.md)

## STRIDE Approach for Threat Modeling
While there are multiple approaches for handling Threat Modeling, the STRIDE
approach pioneered at Microsoft is the most popular approach in software
engineering. STRIDE stands for Spoofing, Tampering, Repudiation, Information
Disclosure, Denial of Service, and Elevation of Privilege.

STRIDE requires one to decompose the system into components, modules and
identify relation (connectivity) between them. You establish what is the trust
boundary for the modules or group of modules and then generate a report. The
report essentially explains the susceptibility to the threats. The design, or
the security team could then evaluate individual threats and investigate them.

<center><img src=./resources/threatmodelflow.png></center>

### When should Threat Modeling be done?
Threat Modeling is not a one-time activity and it has to be tied up to the
design updates of the given system. It is advisible to integrate it as part of
the software development life cycle, especially whenever the new requirements
results in a design or deployment architecture impact. Trust boundaries and
threat indicators will get changed over a course of time as the design evolves
and so should the Threat Model of a given system.

### Who should do it?
Development Team (Systems Engineer): A dev team should consider making Threat
modeling an integral part of the design specifications. Typically the design is
used by the QA team, and by the documentation team for further more derivatives
such as Test design and documentation design. A Threat Model could help the QA
team to better understand the security aspects of the design and prepare test
design for the same.

Security Team: Threat Modeling enables a methodical approach for the security
team to identify possible threats in a given system. The generated threat
report can then be used to evaluate the actual threats.

### How to do Threat Modeling?
Microsoft provides a [Threat Modeling Tool (MS
TMT)](https://docs.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-getting-started)
that allows not only to prepare a model from given templates but it also allows
new templates to be created for different systems. (Brilliant work MS, and
thank you for making the tool available to all).

We have prepared a new template specifically for Kubernetes-native applications
and modeled the open source
[KubeArmor](https://github.com/kubearmor/kubearmor). The
[k8s-template](./templates/k8s-STRIDE-template.tb7) allows us to import k8s
entities such as pods, daemonsets, services, deployments, etc into the model
and use k8s-specific trust boundaries such as "cluster trust boundary", "node
trust boundary", "namespace trust boundary".

The [k8s template](./templates/k8s-STRIDE-template.tb7) and the [KubeArmor
Threat Model](./models/kubearmor/KubeArmor.tm7) along with its [Threat
Report](https://refined-github-html-preview.kidonng.workers.dev/accuknox/k8sthreatmodeling/raw/main/models/kubearmor/KubeArmor%20Threat%20Model.htm)
is available in this repo.

To use the k8s-template and the kubearmor threat model you need to [download
Microsoft Threat Modeling
Tool](https://docs.microsoft.com/en-us/azure/security/develop/threat-modeling-tool).
