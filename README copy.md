# iKubernetes
k8s部署实践相关资料



一键部署

```
# 安装ansible
yum -y install ansible

export release=3.6.2
wget https://github.com/easzlab/kubeasz/releases/download/${release}/ezdown
chmod +x ./ezdown

./ezdown -D -k v1.27.14

./ezdown -S

docker exec -it kubeasz ezctl start-aio
# 如果安装失败，查看日志排除后，使用如下命令重新安装aio集群
# docker exec -it kubeasz ezctl setup default all

$ source ~/.bashrc
$ kubectl version         # 验证集群版本     
$ kubectl get node        # 验证节点就绪 (Ready) 状态
$ kubectl get pod -A      # 验证集群pod状态，默认已安装网络插件、coredns、metrics-server等
$ kubectl get svc -A      # 验证集群服务状态

管理 NODE 节点
管理 MASTER 节点
管理 ETCD 节点
升级 K8S 版本
集群备份与恢复
管理分发用户 kubeconfig
修改 APISERVER 证书
强制更新CA和所有证书
配置负载转发 ingress nodeport

# https://github.com/easzlab/kubeasz/blob/master/docs/op/op-index.md


# https://github.com/easzlab/kubeasz/blob/master/README.md
```

