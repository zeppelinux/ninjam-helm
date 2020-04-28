# ninjam-helm
Helm Chart for Ninjam Server deployment to Kubernetes

Sample deployment to the namespace ninjam:

helm install private /path/to/ninjam-helm -n=ninjam

will create private-ninjam-server deployment and all the resources

helm install public /path/to/ninjam-helm -n=ninjam

will create public-ninjam-server deployment and all the resources

config-volume (for example private-ninjam) is mounted as a file /usr/local/ninjam/config.cfg
