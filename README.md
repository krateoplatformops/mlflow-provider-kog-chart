# MLFlow Provider Chart

This Helm chart provides a template for deploying an application that utilizes OpenAPI Specifications (OAS). It includes ConfigMaps to store the OAS content, a Deployment to run the application, and a Service to expose it.

## Directory Structure

```
my-helm-chart
├── assets
│   ├── experiment.yaml
│   ├── metrics.yaml
│   ├── models.yaml
│   └── run.yaml
├── charts
├── templates
│   ├── configmap-experiment.yaml
│   ├── configmap-metrics.yaml
│   ├── configmap-registeredmodels.yaml
│   ├── configmap-run.yaml
│   ├── deployment.yaml
│   ├── service.yaml
│   └── _helpers.tpl
├── values.yaml
├── Chart.yaml
└── README.md
```

## Installation

To install the chart, use the following command:

```
helm repo add krateo https://charts.krateo.io
helm repo update krateo
helm install krateo-core-provider krateo/mlflow-provider-kog
```

Replace `<release-name>` with your desired release name.

## Configuration

You can customize the chart by modifying the `values.yaml` file. This file contains default configuration values, including server URLs and other parameters.

## Resources

- **ConfigMaps**: Store the OpenAPI Specification content.
  - `configmap-experiment.yaml`: Contains the experiment API specifications.
  - `configmap-metrics.yaml`: Contains the metrics API specifications.
  - `configmap-registeredmodels.yaml`: Contains the registered models API specifications.
  - `configmap-run.yaml`: Contains the run API specifications.
- **Deployment**: Manages the application instances.
- **Service**: Exposes the application to the network.

## Usage

After installation, you can access the application using the service created by this chart. The server URLs defined in the OAS will be templated and utilized by the application.

## Requirements

`oasgen-provider-chart` should be installed in your cluster. Follow the [README](https://github.com/krateoplatformops/oasgen-provider-chart) for installation instructions.