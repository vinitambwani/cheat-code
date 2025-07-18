
## Cluster Commands

#### Displaying cluster info

```$> kubectl cluster-info```

this will give information where Kubernetes Control Plane is running.

#### Listing cluster nodes

```$>kubectl get nodes ```

This will list all the nodes and will information about their status, age and version.

#### Retrieving additional details for the node

```$> kubectl describe node <node-name>```

if you don't mention the node-name then it will describe all the nodes, if the node-name is given then it gives details of that individual node.

## Namespace Commands

#### Listing all namespaces

```$> kubectl get namespaces```

##### Create a new namespace

```$> kubectl create namespace <namespace-name>```

Example:

```$> kubectl create namespace my-apps```

## Pod Commands

#### Listing all the pods

```$> kubectl get pod```

if you want to know, what is the IP address of the pod and to which ode it is running.
then one can use '-o wide' option with the command

```$> kubectl get pod -o wide```

if you want to get all pods of a particular namespace

```$> kubectl get pods --namespace <namespace-name>```

#### Retrieving additional details for the pods

```$> kubectl describe pod <pod-name>```

if you don't mention the pod-name then it will give details of all the pods, if the pod-name is given then it gives details of that individual pod.

#### Listing of pods if the pod contains any particular label

```$> kubectl get pods -l <label-name>```

Example: 

```$> kubectl get pods -l app```

this will list all the pods which contain a label called app.

#### Listing of pods which does not contain a particular label

```$> kubectl get pods -l !<label-name>```

Example:

```$> kubectl get pods -l !env```

This will return all the pods where they don't contain a label called env.


#### Listing of pods if the pod contains a label having a particular value

```$> kubectl get pods -l <label-name>=<value>```

Example:
 list all the pods where the pod contains a label called app which contains a value trial-project

 ```$> kubectl get pods -l app=trial-project```

 similarly we can write list all the pods where the value of label app is not equal to trial-project

 ```$> kubectl get pods -l app!=trial-project```




