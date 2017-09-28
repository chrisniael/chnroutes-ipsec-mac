## Mac 上 L2TP 协议 VPN 分流

检测 l2tp VPN 连接状态，国内 IP 站点直接访问，不走 VPN 流量。

将脚本 `chnroutes-for-ipsec` 放在 `/usr/local/bin` 目录下。

```bash
git clone git@github.com:ranmocy/chnroutes.git
cd chnroutes
python chnroutes.py -p mac -t ipsec
```

将生成的 `phase1-up.sh` 和 `phase1-up.sh` 脚本拷贝到 `/usr/local/bin` 目录中，并去掉后缀 `.sh`

还要要用到的 Mac 的 launchctl 功能，可以使用 brew 安装 launchcontrol 来配置

```bash
brew cask install launchcontrol
```

也可以直接使用命令行增加定时任务。

将 `local.chnroutes-for-ipsec.plist` 放在 `/Library/LaunchDaemons` 目录下。
