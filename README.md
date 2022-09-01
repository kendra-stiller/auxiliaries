
# Auxiliaries

Configuration and deployment instructions for provisioning third-party auxliliary applications onto Kubernetes clusters.

## About

Auxiliaries are either review-only databases or GUI dashboards for providing insights. Each app has 3 files:

- .env  -> with default variables
- .json -> config on how to deploy the app
- .yml  -> either the k8s manifest or helm values file

## Configuration

Documentation for configuration options available to each app can be found in the `/docs` directory.

## Environment Variables

In additional to the variables defined in an auxiliary `.env` file, your pipeline might also need the following set:

```
AUX_SERVICE_URL         domain name for default URLs and auth URL, i.e. staging.example.com
AUX_SERVICE_RELEASE     name to use for auxiliary
AUX_VERSION             version tag used for deployments with Genero helm chart
AUX_PREFIX              optional, a prefix used for review deployments with the Genero helm chart
```

Check the `.yml` file of an auxiliary to determine if any `AUX_` environment variables are needed.
