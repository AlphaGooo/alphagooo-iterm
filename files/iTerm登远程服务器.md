
## 怎么连接远程服务器？
1. 首先写一个sh脚本，比如命名为 item.sh

```
#!/usr/bin/expect -f
set user alphagooo
set host 10.2.0.3
set password 123456
set timeout -1
spawn ssh $user@$host
expect "*assword:*"
send "$password:\r"
interact
expect eof
```

2. 然后保存脚本，比如保存在 ~/.ssh 目录下，打开iTerm，ctrl + o 打开配置，添加profile，选择 Command - Command，写入

```
expect ~/.ssh/item.sh
```

3. 保存后执行就可以了。

## 简单粗暴连接
也可以直接 Genernal->Command下选择 Command，在输入框里填入 ssh username@hostname 比如 ssh root@10.2.0.3
