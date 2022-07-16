# Linux脚本及命令

## scp拷贝
### 跨服务器拷贝文件 推模式
```shell
scp -r /opt/module/jdk root@127.0.0.1:/opt/module
```

### 跨服务器拷贝文件 拉模式
```shell
scp -r root@hadoop102:/opt/module/hadoop-3.1.3 ./
```

### 也可以在B机器上将A机器上的文件拷贝至C机器 在hadoop103机器上执行
```shell
scp -r root@hadoop102:/opt/module/* root@hadoop104:/opt/module
```

## rsync 同步
### 同步命令性能强于scp
```shell
rsync -av hadoop-3.1.3/ root@hadoop103:/opt/module/hadoop-3.1.3/
```

## 免密登录 
在每台服务器上重复下面的步骤
### 生成公钥和私钥
```shell
ssh-keygen -t rsa
```

### 将公钥拷贝至需要免密登录的机器上
```shell
ssh-copy-id hadoop102
ssh-copy-id hadoop103
ssh-copy-id hadoop104
```