# cloud-challenge

# Requirements
- Docker version 28.3.2, build 578ccf6
- Helm 3.18.4

## ~~Try it out!~~ Currently broken due to missing GitHub permissions
You can try and run this locally by doing the following:
1. `helm repo add cloud-challenge https://cryotechnic.github.io/cloud-challenge/`
2. `helm repo update`
3. `helm search repo cloud-challenge`
4. `helm install cloud-challenge/helloapp`

# Local Development

## Helm Chart
When modifying `values.yaml`, either use the `tag` or `digest` property, but not both (as it is configured to only take 1 parameter).

If you do not want to expose external ports for the Pod, you can change the `type` property in `service` to `ClusterIP`.

To deploy, simply run `helm install <name> ./helloapp`. To view Pod status, do `kubectl get all`. If you would like to uninstall, you can do so at any time using `helm uninstall <name>`.

If you have already deployed this once, you can upgrade the Helm chart by running `helm upgrade <original-name> ./helloapp`.

To view Pod logs, `kubectl logs deployment/helloapp`. If you'd like to view it through Helm instead, you can do `helm status <name>`.

## `deploy.yaml` (Deprecated in favor of Helm chart)
The file contains all necesssary syntax to deploy a local instance of `gcr.io/google-samples/hello-app:2.0`.

To know what kind of `apiVersion` we should use, we can run the `kubectl api-resources` command.

The remainder of the schema was auto-generated using VSCode's Kubernetes plugin, but manual creation of a valid YAML structure is also possible. Knowing which fields are required can be achieved using the `kubectl explain <resource> --recursive`. In this case, since a deployment is required, the command to run would be `kubectl explain deployments --recursive`
