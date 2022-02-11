## 문제 
# 쿠버네티스 조인시 아래 메시지와 함께 조인 안됨

[preflight] Running pre-flight checks[preflight] Reading configuration from the cluster...
[preflight] FYI: You can look at this config file with 'kubectl -n kube-system get cm kubeadm-config -o yaml'
error execution phase preflight: unable to fetch the kubeadm-config ConfigMap: failed to decode cluster configuration data: no kind "ClusterConfiguration" is registered for version "kubeadm.k8s.io/v1beta3" in scheme "k8s.io/kubernetes/cmd/kubeadm/app/apis/kubeadm/scheme/scheme.go:31"
To see the stack trace of this error execute with --v=5 or higher

## 해결
# 쿠버네티스 버전 때문
Ubuntu 기준 아래 명령어로 해결

```
kubeadm reset
sudo apt-get purge kubeadm kubectl kubelet kubernetes-cni kube*   
sudo apt-get autoremove  
sudo rm -rf ~/.kube
```
