# 使用kubeadm安装Kubernetes 1.7

kubeadm是Kubernetes官方提供的快速安装和初始化Kubernetes集群的工具，目前的还处于孵化开发状态，伴随Kubernetes每个版本的发布都会同步更新。 当然，目前的kubeadm是不能用于生产环境的。 但伴随着Kubernetes每次版本升级，kubeadm都会对集群配置方面的一些实践做调整，通过实验kubeadm我们可以学习到Kubernetes官方在集群配置上一些新的最佳实践。 例如从Kubernetes 1.6开始kubeadm的目标就是可以快速初始化一个更加安全的Kubernetes集群，Kubernetes 1.6进入beat的RBAC，在这版的kubeadm就有了集成
