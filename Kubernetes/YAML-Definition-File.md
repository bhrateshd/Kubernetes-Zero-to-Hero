**YAML Definition File**

    apiVersion: v1
    kind: Pod
    metadata:
        name: myapp-pod
        labels:
            app: myapp
            type: front-end
        annotations:       # misc info (not used by K8s)
            podVersion: 1.2
    spec:
        containers:
            - name: nginx-container
                image: nginx



- YAML config file to create and maintain objects in a Kubernetes cluster
- It has 4 top level required fields
    - `apiVersion` - string
    - depending upon the kind of K8s object being created, use the right API version


    - `kind` - the kind of K8s object being created (string)
- `metadata` - metadata about the K8s object being created (dictionary)
    - `name` - name of the K8s object (string)
    - `labels` - key-value pairs for grouping K8s objects after creation (dictionary)
    - `annotations` - used to specify misc information not directly used by K8s but could be used by other tools running on the k8s cluster (dictionary)
- `spec` - specifications (dictionary)
    - specific to the K8s object (need to refer the docs)
- Once you have the YAML file, you can deploy the K8s object by `kubectl apply -f`