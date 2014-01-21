## 前菜
- $: 手元のPC
- %: sshした先

```
$ bundle install
```


## vagrant-digitalocean
https://github.com/smdahlen/vagrant-digitalocean

### インストール
 
```
$ vagrant plugin install vagrant-digitalocean
$ brew install curl-ca-bundle
$ echo "export SSL_CERT_FILE=/usr/local/opt/curl-ca-bundle/share/ca-bundle.crt" >> ~/.bash_profile
```

### 起動

```
$ vagrant up --provider=digital_ocean
```

### ssh

```
$ vagrant ssh
```

### 停止

```
$ vagrant destroy
```


## berkshelf
http://berkshelf.com/

### インストール
 
 ```
 $ vagrant plugin install vagrant-berkshelf
 ```