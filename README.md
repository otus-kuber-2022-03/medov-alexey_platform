- [x] Разберитесь почему все pod в namespace kube-system восстановились после удаления.

Все pods в namespace kube-system кроме сoredns востановились потому что их пересоздал kubelet systemd демон работающий на самом хосте. А pod coredns перезапустился потому что есть deployment  с параметром replicas 1, то есть, существует replicaset для coredns который его пересоздает если его нет. Для kube-proxy есть daemonset который запускает его в одном экземпляре на каждой ноде.


