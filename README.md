# ipset_bitmap_port_dccp_sctp

#### 介绍
ipset 中 bitmap:port 类型已经支持 tcp 和 udp 等协议，但是未支持不常见的 dccp 和 sctp。
本次修改新增此类型对于 dccp 和 sctp 的支持以及相关安装、测试说明。

#### 软件架构

内核版本：uname -r
4.18.0-348.el8.x86_64

ipset 版本：
ipset-7.11

#### ipset 安装教程

1. wget https://ipset.netfilter.org/ipset-7.11.tar.bz2
2. tar -jxvf ipset-7.11.tar.bz2
3. cd ipset-7.11
3. ./autogen.sh
3. ./configure
4. make && make modules

编译后生成的内核模块目录为：ipset-7.11/kernel/net/netfilter/ 和 ipset-7.11/kernel/net/netfilter/ipset 目录。

#### 使用说明

1. 根据 ipset 编译生成后的内核模块，需要覆盖到指定目录。
2. cp ipset-7.11/kernel/net/netfilter/xt_set.ko /usr/lib/modules/你的内核版本/kernel/net/netfilter/
3. cp ipset-7.11/kernel/net/netfilter/ipset/*.ko /usr/lib/modules/你的内核版本/kernel/net/netfilter/ipset/

注：如果在测试系统中已有相关的内核模块，需要移除或者删除。
注：可能需要执行 depmod -a 命令或者 reboot。
注：目前 7.1 版本和 7.11 版本接口已经有了变化，需要注意修改内容是不同的。

#### 参与贡献

1. 我
2. 你
3. 他

#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
