# delve_install_mac

在Mac OSX 10.15.7+如何安装 golang delve 调试器

Mac OSX 10.15.7+ 系统下安装delve其实并不困难，我们无需安装HomeBrew，按以下步骤操作即可。

本文假设你已经具备自己安装好golang环境并启用go mod的能力

笔者环境如下：
go version go1.15.3 darwin/amd64

OSX 10.15.7

1.首先安装delve的代码
```shell
$ git clone  https://github.com/derekparker/delve.git
$ cd delve
$ git checkout FETCH_HEAD
$ CERT=dlv-cert make install
```
如果一切顺利，你将会安装好一个旧版本的 delve，它可以使用，但是并不推荐，因为它会提示你版本太旧建议升级。

2.升级delve
```shell
$ go get -u github.com/go-delve/delve/cmd/dlv
```

3.正常使用
```shell
$ dlv debug main.go
```

