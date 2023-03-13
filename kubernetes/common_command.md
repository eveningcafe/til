kubectl config view
kubeadm token list
kubeadm token create
openssl x509 -pubkey -in /etc/kubernetes/pki/ca.crt | openssl rsa -pubin -outform der 2>/dev/null | openssl dgst -sha256 -hex | sed 's/ˆ.* //'
kubeadm join \
--token bemriu.bup84evx9niwexou \
k8scp:6443 \
--discovery-token-ca-cert-hash \
sha256:07ea1d43d4ba2e47a40b4cc6f1f733ba84935aacb4eeb0152d93b916cada8cf6

kubectl get node
kubectl describe node cp
kubectl get events


kubectl create deployment nginx --image=nginx
kubectl get deployments
kubectl describe deployment nginx
kubectl (-n kube-system ) get pod
kubectl get ep  nginx
kubectl edit svc nginx
kubectl get svc  nginx
kubectl delete svc nginx 
kubectl scale deployment nginx --replicas=5

kubectl get pods --all-namespaces
kubectl get pod --show-labels -owide
kubectl get pods -n kube-systems
kubectl get cm -n kube-system
kubectl get cm calico-config -oyaml -n kube-system
kubectl get cm kubelet-config -oyaml  -n kube-system 
kubectl get cm kube-proxy -oymal  -n kube-system

kubectl get job
kubectl get job sleepy -o yaml

kubectl get ds
kubectl edit ds rs-one 
kubectl get ds ds-one -o yaml | grep -A 4 Strategy
kubectl set image ds rs-one nginx=nginx:1.16.1-alpine
kubectl rollout history ds rs-one 
kubectl rollout undo ds rs-one --to-revision=1

kubectl get configmap fast-car -o yaml
kubectl get pvc
kubectl create namespace small
kubectl -n small create -f PVol.yaml
kubectl -n small create -f pvc.yaml
kubectl -n small create -f storage-quota.yaml
kubectl delete pvc pvc-one

kubectl -n linkerd rollout restart deployment linkerd-proxy-injector

crictl ps
crictl images

kubectl get service --all-namespaces

kbectl exec nginx-1423793266-13p6

kubectl create namespace low-usage-limit
kubectl --namespace=low-usage-limit create -f low-resource-range.yaml
kubectl get deployment hog -o yaml >> xx 
edit xx
then 


scheduling:
- vi du nhieu, quan ly rat phuc tap nhung thieu ung dung, chua lam ro duoc la khi nao thi ap dung nao
c:
- Aggregated APIs ko hieu gi--> thieu cai nhin tong quan ve api/ object
security:
- harderning betwent namespace?



kubectl proxy --api-prefix=/ &

kubectl create -f job.yaml

kubectl -n kube-system exec -it etcd-hoanq3lab-ku -- sh \
-c "ETCDCTL_API=3 \
ETCDCTL_CACERT=/etc/kubernetes/pki/etcd/ca.crt \
ETCDCTL_CERT=/etc/kubernetes/pki/etcd/server.crt \
ETCDCTL_KEY=/etc/kubernetes/pki/etcd/server.key \
etcdctl  --endpoints=https://127.0.0.1:2379 member list"

   69  sudo kubeadm token list
   70  sudo kubeadm token create
   71  ip a
   72  cat /etc/hostname 
   73  hostname -i
   74  openssl x509 -pubkey -in /etc/kubernetes/pki/ca.crt | openssl rsa -pubin -outform der 2>/dev/null | openssl dgst -sha256 -hex | sed 's/ˆ.* //'
   75  kubectl get node
   76  kubectl describe node cp
   77  tail
   78  tail
   79  kubectl describe node cp
   80  kubectl describe node hoanq3lab-ku 
   81  kubectl describe node hoanq-labku2 | grep -i taint
   82  kubectl describe node hoanq-labku2 
   83  kubectl taint hoanq-labku2 --all node-role.kubernetes.io/master
   84  kubectl describe node hoanq3lab-ku | grep taint
   85  kubectl describe node hoanq3lab-ku | grep -i taint
   86  kubectl describe node hoanq-labku2 | grep -i taint
   87  kubectl taint nodes --all node-role.kubernetes.io/control-plane
   88  kubectl taint nodes --all node-role.kubernetes.io/master
   89  kubectl describe node | grep -i taint
   90  kubectl taint nodes --all node-role.kubernetes.io/master
   91  kubectl taint nodes --all node-role.kubernetes.io/control-plane
   92  kubectl get pods --all-namespaces
   93  ip a
   94  sudo crictl config --set runtime-endpoint=unix:///run/containerd/containerd.sock --set image-endpoint=unix:///run/containerd/containerd.sock
   95  cat /etc/crictl.yaml 
   96  kubectl create deployment nginx --image=nginx
   97  kubectl get deployments
   98  kubectl describe deployment nginx
   99  kubectl get events
  100  docker ps
  101  containerd --help
  102  ctr containers ls
  103  sudo ctr containers ls
  104  kubectl get events
  105  $ kubectl get deployment nginx -o yaml
  106  $ kubectl get deployment nginx -o yaml > first.yahml
  107  kubectl get deployment nginx -o yaml > first.yaml
  108  nano first.yaml 
  109  kubectl delete deployment nginx 
  110  kubectl create -f first.yaml 
  111  kubectl get deployment nginx -o yaml > second.yaml
  112  diff first.yaml second.yaml 
  113  kubectl create deployment two --image=nginx --dry-run=client -o yaml
  114  kubectl get deployment
  115  kubectl expose -h
  116  kubectl expose deployment/nginx
  117  nano first.yaml 
  118  nano +31 first.yaml 
  119  kubectl replace -f first.yaml
  120  kubectl expose deployment/nginx
  121  kubectl get svc nginx
  122  kubectl get ep nginx
  123  tail
  124  kubectl describe pod nginx-6c8b449b8f-962d6 
  125  kubectl describe pod nginx-6c8b449b8f-962d6  | grep Node
  126  tail
  127  curl 10.0.1.18:80
  128  telnet 10.0.1.18 22
  129  telnet 10.0.1.18 234
  130  telnet 10.0.1.18 80
  131  kubectl get svc nginx
  132  kubectl get ep nginx
  133  curl 10.98.136.80:80
  134  kubectl get svc
  135  ip a
  136  kubectl get ep nginx
  137  curl 192.168.164.67:80
  138  curl 192.168.164.67 80
  139  curl 192.168.164.22 80
  140  curl 192.168.164.64 80
  141  telnet 192.168.164.67 80
  142  kubectl endpoint list
  143  kubectl ep  list
  144  kubectl  get ep  nginx
  145  kubectl get deployment nginx
  146  kubectl scale deployment nginx --replicas=3
  147  $ kubectl get deployment nginx
  148  kubectl get deployment nginx
  149  kubectl get ep nginx
  150  kubectl delete pod nginx-6c8b449b8f-962d6
  151  kubectl get ep nginx
  152  kubectl exec nginx-6c8b449b8f-5mjnz -- printenv 
  153  kubectl exec nginx-6c8b449b8f-5mjnz -- printenv  
  154  kubectl exec nginx-6c8b449b8f-5mjnz -- printenv   | grep KUBE
  155  kubectl delete svc nginx
  156  kubectl expose deployment nginx --type=LoadBalancer
  157  sudo apt-get install net-s
  158  sudo -i
  159  kubectl get svc
  160  curl ifconfig.i
  161  cat ~/.kube/config
  162  ls
  163  cd s_03/
  164  ls
  165  history | grep apply
  166  ls
  167  cat calico.yaml 
  168  ip a
  169  kubectl en list
  170  kubectl get ep nginx
  171  kubectl get pods
  172  kubectl get service --all-namespaces
  173  kubectl get pod nginx  -o custom-columns=NAME:metadata.name,IP:status.podIP
  174  kubectl get pod nginx-6c8b449b8f-mslbj  -o custom-columns=NAME:metadata.name,IP:status.podIP
  175  telnet 192.168.164.72 80
  176  byobu
  177  kubectl get service --all-namespaces
  178  telnet 10.96.28.133 89
  179  telnet 
  180  history 
  181  kubectl get ep nginx
  182  telnet 192.168.164.71 80
  183  route -n
  184  kubectl get pod 
  185  kubectl exec -it nginx-6c8b449b8f-mslbj -- sh
  186  ip a
  187  curl 10.0.1.17 31152 
  188  curl 10.0.1.17:31152 
  189  curl 10.0.1.18:31152 
  190  route -n
  191  kubectl get ns
  192  kubectl -n kube-system
  193  kubectl -n kube-system get pod 
  194  crictl ps
  195  sudo su
  196  kubectl describe node | grep -i taint
  197  kubectl get pods --all-namespaces
  198  history | grep nginx
  199  kubectl scale deployment nginx --replicas=5
  200  kubectl get pods --all-namespaces
  201  crictl ps
  202  sudo crictl ps
  203  history | grep cri
  204  curl 10.0.1.18:31152 
  205  curl 10.0.1.17:31152 
  206  netstat -ntpl
  207  ls
  208  cat calico.yaml 
  209  nano  calico.yaml 
  210  kubectl get svc
  211  curl 10.96.0.1:443
  212  curl 10.96.0.1
  213  curl https://10.96.0.1
  214  curl https://10.96.0.1 -k
  215  kubectl get ns
  216  kubectl get pod -A
  217  kubectl get svc
  218  curl 10.96.28.133
  219  kubectl -n kube-system get pod
  220  kubectl -n kube-system get pod -owide
  221  kubectl -n kube-system logs calico-node-gl8rx
  222  kubectl get svc
  223  kubectl edit svc nginx
  224  ls
  225  vim second.yaml 
  226  kubectl edit svc nginx
  227  kubectl get pod --show-label
  228  kubectl get pod --show-labels
  229  kubectl get pod -owide
  230  kubectl get nodes
  231  kubectl get pods -n kube-systems
  232  kubectl get pods -n kube-system
  233  kubectl get cm -n kube-system
  234  kubectl get cm calico-config -oyaml -n kube-system
  235  kubectl get cm -n kube-system
  236  kubectl get cm kubelet-config -oyaml  -n kube-system 
  237  kubectl get cm -n kube-system
  238  kubectl get cm kube-proxy -oymal  -n kube-system
  239  kubectl get cm kube-proxy -oyaml  -n kube-system
  240  kubectl get svc
  241  kubectl get ns 
  242  kubectl get svc
  243  kubectl delete svc nginx 
  244  ls
  245  kubectl get svc
  246  curl 10.0.1.17:30098
  247  ip a
  248  curl 10.0.1.18:30098
  249  curl 10.0.1.17:30098
  250  curl localhost:30098
  251  kubectl get svc
  252  kubectl edit svc nginx
  253  kubectl get nodes
  254  kubectl describe node hoanq3lab-ku 
  255  kubectl delete svc nginx 
  256  kubectl expose deployment nginx --type=LoadBalancer
  257  kubectl edit svc nginx
  258  kubectl expose deployment nginx --type=LoadBalancer
  259  kubectl get nodes
  260  kubectl describe node hoanq3lab-ku 
  261  kubectl get svc
  262  ls
  263  kubectl describe node 
  264  history 
