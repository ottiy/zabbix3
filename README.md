
「さくらのクラウドでのDockerハンズオン」および「さくらのクラウドのハンズオン」で使用するyamlファイルです。
<br>
内容は[「Zabbix 3.0をDocker Composeで一度に実行する方法」](http://qiita.com/zembutsu/items/686b99be90d72688aee8)の中にある。Zabbix3.0をDocker composeを利用してインストールするyamlファイルのコピーとなります。
<br>
<br>
以下は、主に「さくらのクラウド」でのハンズオンで使用するコマンドとなります。

## ローカルネットワークを組む



```
ifconfig –a
```
上記コマンドで「eth1」が登録されているか確認する。


```
ifconfig eth1 192.168.0.1/24
```

上記コマンドで「eth1」のIPアドレスを設定する。

```
ping 192.168.0.2
```
上記コマンドで、Pingを打つ。CTRL + Cで止まる。


## Dockerのインストールと起動

```
curl -sSL https://get.docker.com/ | sh
```
上記コマンドでDockerをインストールできる。



```
systemctlstart docker
```
上記コマンドでDockerを起動する



```
dockerrun -p 80:2368 -d ghost
```

ghostをスタートする。



## Docker compose

```
curl -L https://github.com/docker/compose/releases/download/1.6.2/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
```

```
chmod +x /usr/local/bin/docker-compose 
```


上記2つのコマンドでDocker composeをインストール


