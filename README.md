# java-oracle-on-Rancher

まず初めに、`/java-oracle-on-Rancher/build/payara/`配下でdocker imageをビルドする。archによっては、docker imageを変更する必要があります。

```
docker build -t payara-micro:k8s .
```

docker imageの作成完了後、`/java-oracle-on-Rancher`配下でKubernetesリソースをデプロイする。

```
kubectl create -f .
```