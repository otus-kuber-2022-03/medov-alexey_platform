<h4> Домашнее задание по теме "Знакомство с Kubernetes, основные понятия и архитектура" </h4>

Задание 1:

- Разберитесь почему все pod в namespace kube-system восстановились после удаления.

- Все pods в namespace kube-system кроме сoredns востановились потому что их пересоздал kubelet systemd демон работающий на самом хосте. А pod coredns перезапустился потому что есть deployment  с параметром replicas 1, то есть, существует replicaset для coredns который его пересоздает если его нет. Для kube-proxy есть daemonset который запускает его в одном экземпляре на каждой ноде.

Задание 2:

- Написать валиадный манифест kubernetes-intro/web-pod.yaml

- Написал

Задание 3:

- Написать валиадный и рабочий манифест kubernetes-intro/frontend-pod-healthy.yaml

- Написал
