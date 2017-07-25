#### Client

**./client -l 10.0.0.210:8081** 设定本地监听地址和端口，默认：`:12949`

**./client -r 10.0.0.210:8082** 设定远程监听地址和端口，默认：`vps:29900`

**./client - -key hello** 设定预共享秘钥

**./client —crypt **aes, aes

-128, aes-192, salsa20, blowfish, twofish, cast5, 3des, tea, xtea, xor, none (default: "aes")  设定加密算法，默认：`aes`

**.. —mode **fast3, 设置加速模式 fast2, fast, normal, manual (default: "fast")

**.. —conn 2** 设定UDP 连接的数目，默认：`1`

**.. —autoexpire 1000** 设定单个UDP连接的自动截止时间（秒）

**.. — scavengettl  1000** 设定一个截止的连接可以存在的时间

**.. —mtu** 设定UDP 最大的传输单元 默认值`1350`

**.. — sndwnd ** 设定发送窗口的大小（包数）默认`128`

**.. — rcvwnd** 设定接收窗口的大小（包数）默认`512`

**.. — ds，ps ** 设置里德-所罗门码

**.. — dscp ** 设置dscp（差分业务编码） 默认`0`

**.. — nocomp** 禁止压缩

**.. — snmplog value ** 收集日志

**.. — snmpperiod** 收集日志的周期

**.. — log** 

**.. — c value** 用json文件进行配置，可以覆盖shell中的命令

**.. — h, — v** 帮助、输出版本



#### 客户端和服务端必须保持一致的参数

- datashard 里德-所罗门码
- parityshard 里德-所罗门码
- nocomp 禁止压缩
- key 预共享秘钥
- crypt 加密算法





