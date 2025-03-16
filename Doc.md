https://argo-cd.readthedocs.io/en/stable/
https://docs.rke2.io/
https://chatgpt.com/c/67d4c8e4-c918-800c-bb09-9eab2ae93241
https://docs.rke2.io/architecture

## Araid06 :

- désactivation de SELinux : (non necessaire)
<!-- - désactivation de SELinux :
```bash
sudo setenforce 0
``` -->

Ajout de la configuration pour NetworkManager :

```bash
 echo -e "[keyfile]\nunmanaged-devices=interface-name:flannel*;interface-name:cali*;interface-name:tunl*;interface-name:vxlan.calico;interface-name:vxlan-v6.calico;interface-name:wireguard.cali;interface-name:wg-v6.cali" | sudo tee /etc/NetworkManager/conf.d/rke2-cni.conf
```


ArgoCd Cli:

```bash
curl -sSL -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64
chmod +x /usr/local/bin/argocd
```

ArgoCd site mdp :

```bash
kubectl get secret -n argocd argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
https://192.168.10.103:30849/applications




Il faut comprendre : control plane, ectd et master (role actuelle de notre node) 

nom du node master : rke2-master

kubectl get nodes pour avoir la liste des noeuds 


helm ?







After running this installation:

The rke2-server service will be installed. The rke2-server service will be configured to automatically restart after node reboots or if the process crashes or is killed.
Additional utilities will be installed at /var/lib/rancher/rke2/bin/. They include: kubectl, crictl, and ctr. Note that these are not on your path by default.
Two cleanup scripts, rke2-killall.sh and rke2-uninstall.sh, will be installed to the path at:
/usr/local/bin for regular file systems
/opt/rke2/bin for read-only and brtfs file systems
INSTALL_RKE2_TAR_PREFIX/bin if INSTALL_RKE2_TAR_PREFIX is set
A kubeconfig file will be written to /etc/rancher/rke2/rke2.yaml.
A token that can be used to register other server or agent nodes will be created at /var/lib/rancher/rke2/server/node-token