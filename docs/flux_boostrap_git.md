
### Configuration

all configuration is derived from [this resource](https://registry.terraform.io/providers/fluxcd/flux/latest/docs/resources/bootstrap_git)

```
apiVersion: flux.upbound.io/v1beta1
kind: Bootstrap
metadata:
  name: flux-bootstrap
  labels:
    testing.upbound.io/example-name: flux-bootstrap
spec:
  url: "" #: "" # Url of git repository to bootstrap from. Only required option in list
  authorEmail: "" # Author email for Git commits.
  authorName: "" # Author name for Git commits.
  branch: "" # Branch in repository to reconcile from.
  clusterDomain: "" # The internal cluster domain.
  commitMessageAppendix: "" # String to add to the commit messages.
  components: [] # [EX1,EX2] Toolkit components to include in the install manifests.
  componentsExtra: [] # [EX1,EX2] List of extra components to include in the install manifests.
  gpgKeyId: "" # Key id for selecting a particular key.
  gpgKeyRing: "" # GPG key ring for signing commits.
  gpgPassphrase: "" # Sensitive/Secret string  Passphrase for decrypting GPG private key.
  imagePullSecret: "" # Kubernetes secret name used for pulling the toolkit images from a private registry.
  interval: "" # Interval at which to reconcile from bootstrap repository.
  kustomizationOverride: "" # Kustomization to override configuration set by default.
  logLevel: "" # Log level for toolkit components.
  namespace: "" # The namespace scope for install manifests.
  networkPolicy: "" # Boolean Deny ingress access to the toolkit controllers from other namespaces using network policies.
  path: "" # Path relative to the repository root, when specified the cluster sync will be scoped to this path.
  recurseSubmodules: "" # Boolean Configures the GitRepository source to initialize and include Git submodules in the artifact it produces.
  registry: "" # Container registry where the toolkit images are published.
  secretName: "" # Name of the secret the sync credentials can be found in or stored to.
  tolerationKeys: [] # [EX1,EX2] List of toleration keys used to schedule the components pods onto nodes with matching taints.
  version: "" # Flux version.
  watchAllNamespaces: "" # Boolean If true watch for custom resources in all namespaces.
  http:
    allowInsecureHttp: "" # Boolean Allows http Git url connections.
    certificateAuthority: "" # Certificate authority to validate self-signed certificates.
    password: "" # Sensitive/Secret string  Password for basic authentication.
    username: "" # Username for basic authentication.
  ssh:
    password: "" # Sensitive/Secret string  Password for private key.
    privateKey: "" # Sensitive/Secret string  Private key used for authenticating to the Git SSH server.
    username: "" # Username for Git SSH server.

  # Read-Only
  id: "" # The ID of this resource.
  repositoryFiles: [] # [VAL=EX1,VAL=EX2] Git repository files created and managed by the provider.
```