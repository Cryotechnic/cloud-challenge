# cloud-challenge

# Requirements
- Docker version 28.3.2, build 578ccf6

## `deploy.yaml`
The file contains all necesssary syntax to deploy a local instance of `gcr.io/google-samples/hello-app:2.0`.

To know what kind of `apiVersion` we should use, we can run the `kubectl api-resources` command.

The remainder of the schema was auto-generated using VSCode's Kubernetes plugin, but manual creation of a valid YAML structure is also possible. Knowing which fields are required can be achieved using the `kubectl explain <resource> --recursive`. In this case, since a deployment is required, the command to run would be `kubectl explain deployments --recursive`