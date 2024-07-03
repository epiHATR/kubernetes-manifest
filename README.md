# Introduction
This is K8S manifest repository for bootstrapping ArgoCD, Let's Encrypt and common configurations in a Kubernetes cluster.

# Configurations
### ArgoCD
This creates a ArgoCD config map that define accounts and its role on an ArgoCD server instances.
```yaml
data:
  accounts.administrator: login,apiKey
  accounts.maintainer: login,apiKey
  accounts.reader: login,apiKey

```

### Let's Encrypt
This creates a ClusterIssuer for Cert-Manager and to be used by the K8S 

### Commons
#### This defines common configurations for a kubernetes cluster like: 
- Roles
- RoleBinding
- ClusterRoles
- ClusterRoleBindings
- NetworkPolicy

#### For ClusterRole, this will create 2 ClusterRole:
- Cluster-Reader: Read/List/Watch all cluster resources for authenticated users.
- Cluster-Super-Admin: Full actions on all cluster resources for a specific Azure AD group, consider changing this value matches with your Azure AD group.