# Linux脚本

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
