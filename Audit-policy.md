## What Is Kubernetes Audit Logging
- Audit logging, however, is not on by default. Because of that, you can retrieve all of the audit logs you’d like, but you must set up a policy configuration.
### Accessing Audit Logs
- Below is an example command that you would need to run to point the Kubernetes cluster to the audit policy and point to where the logs should be stored.
```
kube-apiserver --audit-log-path=/var/log/kubernetes/apiserver/audit.log \
               --audit-policy-file=/etc/kubernetes/audit-policies/name_of_policy.yaml
```
### Collecting Audit Logs from a Cloud Provider
1. If you’re running a Kubernetes cluster in Azure using Azure Kubernetes Service (AKS), not only are the audit logs turned on for you automatically, but container logging is enabled so you can start querying audit logs right away.
2. In AWS if you’re using EKS, it’s a bit different. When you’re creating an EKS cluster, you’ll have to manually set the option to turn on Audit logging. This isn’t necessarily a bad thing, and you should definitely turn on this configuration. For AWS, you can send audit logs to CloudWatch Logs or other destinations.
3. With GKE you can use GKE Cloud Audit Logs and with Rancher, you can enable rancher logging for both kube-api servers and clusters that are running in your environment. 
