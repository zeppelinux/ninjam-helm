# ninjam-helm
Helm Chart for Ninjam Server deployment to Kubernetes

#### Sample deployment:

`helm install private /path/to/ninjam-helm`

creates _private-ninjam-server_ deployment and all the resources in default namespace

`helm install public /path/to/ninjam-helm`

creates _public-ninjam-server_ deployment and all the resources

#### Configuration

ConFigMap as a config-volume is mounted as /usr/local/ninjam/config.cfg
If you want to edit config.cfg (disable session recordings for ex.) - edit Config Map and restart the Pod (or send signal to the process)

#### Jam Session Persistence

All the sessions are persisted in /usr/local/ninjam/sessions out of the box in the container.
If you want to make sure sessions survive pod restart - enable persistence in the values.yaml and specify **storageClass**.

#### Expose to the world
Default service type is NodePort, if you want to expose your Pod to the outside - capture the port number and the Node IP 
and use them to configure firewall/port mapping rule in your network router.
Default _externalTrafficPolicy_ is _Local_, i.e. if you want to expose all your Pods using one Node change it to _Cluster_

