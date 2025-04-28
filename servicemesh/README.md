# OpenShift Service Mesh Helm Chart

This Helm chart deploys the OpenShift Service Mesh operator and configures a ServiceMeshControlPlane and ServiceMeshMemberRoll.

## Prerequisites

- OpenShift Container Platform 4.x or later
- Helm 3.x or later
- OpenShift GitOps (ArgoCD) installed for GitOps-based deployment

## Configuration

The following table lists the configurable parameters of the Service Mesh chart and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `operator.name` | Name of the Service Mesh operator | `servicemeshoperator` |
| `operator.namespace` | Namespace for the Service Mesh operator | `openshift-operators` |
| `operator.channel` | Channel for the operator subscription | `stable` |
| `operator.installPlanApproval` | Install plan approval strategy | `Automatic` |
| `operator.source` | Source catalog for the operator | `redhat-operators` |
| `operator.sourceNamespace` | Namespace of the source catalog | `openshift-marketplace` |
| `operator.startingCSV` | Specific version of the operator to install | `servicemeshoperator.v2.6.0` |

## Usage

To deploy this chart manually with Helm:

```bash
helm install servicemesh -n openshift-gitops ./servicemesh
```

To deploy with ArgoCD, apply the application-servicemesh.yaml file:

```bash
oc apply -f servicemesh/application-servicemesh.yaml
```

## Notes

This chart follows the same pattern as the RHOAI and OpenShift Serverless charts, with a similar structure and configuration approach.
