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
```

