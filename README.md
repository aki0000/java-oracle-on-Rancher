# java-oracle-on-Rancher

まず初めに、`/java-oracle-on-Rancher/build/payara/`配下でdocker imageをビルドする。archによっては、docker imageを変更する必要があります。

```
docker build -t payara-micro:k8s .
```

### Payara Dokcer Imageについて
```
payara/micro -> 公式
schipplock/payara-micro:5.2022.1-jdk11 -> M1 Mac-amd64の回避策 (非公式のimageなので、微妙)
```
参照元: https://hub.docker.com/search?q=payara&type=image

docker imageの作成完了後、`/java-oracle-on-Rancher`配下でKubernetesリソースをデプロイする。

```
kubectl create -f .
```

### Oracle Databaseについて
以下から、該当するOracle DatabaseのImageを取得する。
https://container-registry.oracle.com/

また、現時点で公式GitHub issueで取り上げられているが、M1 Macについてサポートしていない。公式Imageが動作しないことも確認済。
https://github.com/oracle/docker-images/discussions/1951