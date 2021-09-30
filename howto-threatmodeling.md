# Practical Threat Modeling

This guide will be focussing on the STRIDE approach for threat modeling and
will be using Microsoft's [MSTMT
app](https://docs.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-getting-started).
We have prepared a [k8s-stencils-template](./templates/k8s-STRIDE-template.tb7)
that could be used with the tool making it easier to model applications,
services, agents based on k8s.

![](./resources/mstmt-demo.gif)

Threat Modeling is handled in following steps:

1. **Tool-Preparation**:
	* Download [MS-TMT app](https://aka.ms/threatmodelingtool)
	* Download [k8s-stencils-template](./templates/k8s-STRIDE-template.tb7)
	
![](./resources/mstmt-screen1.png)

2. **MODEL-Preparation**: This step involves
	* preparing a system's interaction diagram or deployment architecture
	* specifying the trust boundaries
	Reuse existing system design diagrams and apply trust boundaries as
	necessary. Note that it is not necessary to get all the interactions
	correct in the first phase. You can have a simplistic view and then later
	keep on adding new entities/components to your model and apply new trust
	boundaries.

<center><img src=./models/kubearmor/ka-threat-model.png></center>

3. **Report Generation**: Once the model is prepared click on "Switch to
   Analysis View" to check all the detected threats.

   To get a detailed report use, "Reports -> Create Full Report...". The report would be saved in an HTML file.
   For sample report, [check here](https://refined-github-html-preview.kidonng.workers.dev/accuknox/k8sthreatmodeling/raw/main/models/kubearmor/KubeArmor%20Threat%20Model.htm).

4. **Threat analysis**: For the reported threats provide an analysis, stating whether
	* the threat needs investigation
	* it is "not applicable" and provide a justification
	* it is Mitigated because of some action taken

<center><img src=./resources/mstmt-threatanalysis.png></center>

