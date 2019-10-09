# adam-lab
	
Create namespace `dev`:
> $ kubectl create ns dev

Deploy uninstrumented application into the namespace:

> $ kubectl -n dev apply -f demoapp/

Create namespace `appdynamics`

> $ kubectl create ns appdynamics:

Create user account in AppD as descirbed [here](https://github.com/Appdynamics/cluster-agent/blob/master/docs/rest-user-role.md)

Update secret.yaml with the new user credentials and the controller access key
Run the command in the updated secret.yaml in the terminal.

Deploy the AppDynamics operator

> $ kubectl -n appdynamics apply -f cluster-agent-operator.yaml

on OpenShift


> $ kubectl -n appdynamics apply -f cluster-agent-operator-openshift.yaml


Deploy infrastructure visibility. Update the controller Url and the account info in infra.yaml and deploy
> $ kubectl -n appdynamics apply -f infra.yaml


Deploy ADAM. Update the controller Url in adam.yaml.
> $ kubectl -n appdynamics apply -f adam.yaml


