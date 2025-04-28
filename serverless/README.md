# OpenShift Serverless Helm Chart

This Helm chart deploys the OpenShift Serverless operator and configures Knative Serving and Knative Eventing.

## Prerequisites

- OpenShift Container Platform 4.x or later
- Helm 3.x or later
- OpenShift GitOps (ArgoCD) installed for GitOps-based deployment

## Configuration

The following table lists the configurable parameters of the Serverless chart and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `namespace.name` | Namespace for the OpenShift Serverless operator | `openshift-serverless` |
| `namespace.create` | Whether to create the namespace | `true` |
| `operator.name` | Name of the Serverless operator | `serverless-operator` |
| `operator.channel` | Channel for the operator subscription | `stable` |
| `operator.installPlanApproval` | Install plan approval strategy | `Automatic` |
| `operator.source` | Source catalog for the operator | `redhat-operators` |
| `operator.sourceNamespace` | Namespace of the source catalog | `openshift-marketplace` |
| `operator.startingCSV` | Specific version of the operator to install | `serverless-operator.v1.34.1` |
| `knativeServing.enabled` | Whether to enable Knative Serving | `true` |
| `knativeServing.name` | Name of the Knative Serving instance | `knative-serving` |
| `knativeServing.namespace` | Namespace for Knative Serving | `knative-serving` |
| `knativeEventing.enabled` | Whether to enable Knative Eventing | `true` |
| `knativeEventing.name` | Name of the Knative Eventing instance | `knative-eventing` |
| `knativeEventing.namespace` | Namespace for Knative Eventing | `knative-eventing` |

## Usage

To deploy this chart manually with Helm:

```bash
helm install serverless -n openshift-gitops ./serverless
```

To deploy with ArgoCD, apply the application-serverless.yaml file:

```bash
oc apply -f serverless/application-serverless.yaml
```

## Notes

This chart follows the same pattern as the RHOAI chart, with a similar structure and configuration approach.
