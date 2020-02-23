# trojan

trojan多用户管理部署程序

## 功能
- 启动 / 停止 / 重启 trojan 服务端
- 支持流量统计和流量限制
- 命令行模式管理, 支持命令补全
- 多用户管理
- 集成acme.sh证书申请
- 生成客户端配置文件

## 安装方式
*trojan使用请提前准备好服务器可用的域名*

###  a. 一键脚本安装
```
#安装
source <(curl -sL https://git.io/trojan-install)

#卸载
source <(curl -sL https://git.io/trojan-install) --remove

```
安装完后输入'trojan'即可进入管理程序

### b. 二进制文件运行
到release页面直接下载二进制文件后, 放到linux服务器上  
**因为trojan本身仅支持x86_64, 所以只编译了x86_64版本的管理程序**
```
chomd +x trojan
./trojan
```
若需要命令补全, 则需将trojan文件放置在/usr/local/bin/目录下, 然后运行
```
#bash环境
echo "source <(trojan completion bash)" >> ~/.bashrc
source ~/.bashrc

#zsh环境
echo "source <(trojan completion zsh)" >> ~/.zshrc
source ~/.zshrc
```
如果还是无法补全, 可能系统缺少bash-completion依赖, 需手动安装

### c. docker运行
开发中

## 命令行
```
Usage:
  trojan [flags]
  trojan [command]

Available Commands:
  add         添加用户
  completion  自动命令补全(支持bash和zsh)
  del         删除用户
  help        Help about any command
  info        用户信息列表
  restart     重启trojan
  start       启动trojan
  status      查看trojan状态
  stop        停止trojan
  tls         证书安装
  update      更新trojan

Flags:
  -h, --help   help for trojan
```
