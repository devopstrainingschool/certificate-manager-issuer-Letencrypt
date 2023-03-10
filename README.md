# certificate-manager-issuer-Letencrypt
https://cert-manager.io/docs/installation/helm/
## Installing Cert-Manager
### follow this : https://cert-manager.io/docs/installation/helm/

## Install Issuer:
```
apiVersion: cert-manager.io/v1
kind: ClusterIssuer
metadata:
  name: letsencrypt-prod
  namespace: default
spec:
  acme:
    email: user@yannickeboo.com #make sure to add right email here
    server: https://acme-v02.api.letsencrypt.org/directory
    privateKeySecretRef:
      name: letsencrypt-secret-prod
    solvers:
    - http01:
        ingress:
          class: nginx
  ```
