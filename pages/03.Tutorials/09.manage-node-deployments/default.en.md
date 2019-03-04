---
title: 'Manage node deployments'
published: true
date: '18-07-2018 13:00'
taxonomy:
    tag:
        - kubernetes
        - gui
        - node
---

## Add new node deployment

To add a new node deployment navigate to your cluster view and click on the `Add Node Deployment` button:

![Cluster overview with highlighted add button](image_add_np_overview.png)

In the popup you can then choose the number of nodes (replicas), kubelet version, flavor, etc for your newly created nodedeployment. All nodes created in this nodedeployment will have the chosen settings.


## Edit the node deployment

To add or delete a worker node you can easily edit the node deployment in your cluster. Navigate to the cluster overview and click on the node deployment you want to change. You will then see the node deployment overview. In this overview click on the `Edit Node Deployment` button:

![Node deployment overview with highlighted edit button](image_edit_np_button_hightlight.png)

In the popup you can now in- or decrease the number of, as well as the kubelet version, operating system, used image etc of the worker nodes which are managed by this node deployment:

![Node deployment overview with opened edit modal](image_edit_np_modal.png)

Save your changes and wait for MetaKube to add or delete your extra worker node(s):

![Overview of currently built worker node](image_edit_np_wait_for_node.png)

The nodes will be upgraded in a rolling upgrade, which means it does a one-by-one upgrade of all machines. Therefor it will create a new node and when this node is ready will drain and delete an old node and so on until all nodes are updated.