# Traffic-forwarding

## 第一步



```bash
ssh -CqTnNf Hostname@Hostip -D 本机端口
例：ssh -CqTnNf johnli@10.2.7.158 -D 5502
然后输入远程服务器密码
```

其中 `-C` 为压缩数据，`-q` 安静模式，`-T` 禁止远程分配终端，`-n` 关闭标准输入，`-N` 不执行远程命令。此外视需要还可以增加 `-f` 参数，把 ssh 放到后台运行。

## 第二步

在本机设置socks代理端口为第一步设置的端口

<img src="https://github.com/dddkyi/Traffic-forwarding/blob/main/image-20211107210445056.png" alt="image-20211107210445056" style="zoom:50%;" />

## 停止转发



```bash
ps -ef |grep ssh
```

<img src="https://github.com/dddkyi/Traffic-forwarding/blob/main/image-20211107210714601_副本.png" alt="image-20211107210714601_副本" style="zoom:50%;" />

找到对应的pid,执行：

```bash
kill -9 pid
例：kill -9 44747
```



## 验证

在百度中输入 ip 查看所属运营商

实验室为鹏博士 buaa为电信

若为鹏博士 则流量转发成功
