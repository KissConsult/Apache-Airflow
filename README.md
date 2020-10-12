# Get Apache Airflow on IBM Cloud

[IBM Cloud] offers the most open and secure public cloud for business . 
At the end of the tutorial you will have a cluster with a Apache Airflow up and runnning.

## Prerequisites

* You should have an IBM Cloud account , if not please [Register Here]
* Have a running Kubernetes Cluster on the IBM Cloud, if you need help with provisioning one ,please follow this [guide] to get you started.
* Have IBM Cloud Block Storage plug-in on you cluster, you can follow our guide for deploying the plug-in [here]

## Deploying Apache Airflow

We will deploy  Apache Airflow on our cluster 
  
* Click the **Catalog** button on the top 
* Select **Software** from the catalog
* Search for **Apache Aifrlow** and click on it
![Search](/search.png)


* On the application page Click in the _dot_ next to the cluster , you wish to use
![Cluster](/cluster-select.png)
* Click on  **Enter or Select Namespace** and choose the default Namespace or use a custom one 
![Namespace](/details-namespace.png)
* Give a unique **name** to workspace , which you can easily recognize
![Name](/details-name.png)
* Select which resource group you want to use , it's for access controll and billing purposes. For more information please visit [resource groups]

![apache-resource](/details-resource.png)

* Give **tags** to your apache workspace , for more information visit [tags]

![apache-tags](/details-tags.png)

* Click on **Parameters with default values** , You can set deployment values or use the default ones

![def-val](/parameters.png)

* After finishing everything , **tick** the box next to the agreements and click **install**

![Install](/aggreement-create.png)

* The apache workspace will start installing , wait a couple of minutes 

![airflow-progress](/in-progress.png)

* You apache workspace has been successfully deployed

![airflow-finsihed](/airflow-done.png)

## Verify Apache installation

* Go to [Resources] in your browser 
* Click on **Clusters**
* Click on your Cluster
![Resourcelect](/resource-select.png)

* Now you are at you clusters overview ,here Click on **Actions** and **Web terminal** from the dropdown menu


![Actions](/cluster-main.png)

* Click **install** - wait couple of minutes 

![terminal-install](/terminal-install.jpg)

* Click on **Actions**
* Click **Web terminal** --> a terminal will open up

* **Type** in the terminal , please change NAMESPACE to the namespace you choose at the deployment setup:

 ```sh
$ kubectl get ns
```
![get-ns](/get-ns.png)


 ```sh
$ kubectl get pod -n NAMESPACE -o wide 
```
![get-pod](/get-pod.png)


 ```sh
$ kubectl get service -n NAMESPACE
```
![get-service](/get-service.png)


* Running Apache Airflow pods  will be visible 


You successfully deployed an Apache Airflow on IBM Cloud ! 


[IBM Cloud]: <http://cloud.ibm.com>
[Register Here]: <http://cloud.ibm.com/registration>
[guide]: <https://github.com/KissConsult/clusterIBM>
[here]: <https://github.com/KissConsult/IBM-Cloud-Block-Storage-plug-in>
[resource groups]: <https://cloud.ibm.com/docs/account?topic=account-account_setup#bp_resourcegroups>
[tags]: <https://cloud.ibm.com/docs/account?topic=account-tag>
[Resources]: <http://cloud.ibm.com/resources>
