<img src="https://v2.jinrishici.com/one.svg?font-size=24&spacing=2&color=Black">


* 合并ssr、passwall、vssr以及依赖项

#### 使用方式
```yaml

默认ssr与passwall的插件与依赖整合包

使用方法：将整合包上传到openwrt设备的tmp目录，输入命令 opkg install *.ipk

默认压缩包里包含ssr passwall bypass passwall2 插件

如果单独安装ssr与依赖，rm -rf {*passwall*,*bypass*,*vssr*}
```


##### 插件每日更新下载:
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/kenzok8/small?style=for-the-badge&label=插件下载)](https://github.com/zhiern/Zoom-PK/releases/tag/4-x86_64)

+ [ssr+passwall依赖仓库](https://github.com/zhiern/Helloword)


#### 使用
一键命令(防止插件冲突，删除重复)
```yaml
sed -i '1i src-git zoom https://github.com/zhiern/Helloword' feeds.conf.default
./scripts/feeds update -a && rm -rf feeds/luci/applications/luci-app-mosdns
rm -rf feeds/packages/net/{alist,adguardhome,mosdns,xray*,v2ray*,v2ray*,sing*,smartdns}
rm -rf feeds/packages/utils/v2dat
rm -rf feeds/packages/lang/golang
git clone https://github.com/zhiern/golong feeds/packages/lang/golang
./scripts/feeds install -a 
make menuconfig
```

#### 注意
编译新版Sing-box和hysteria，尽量使用golang版本1.22以上版本 ，可以用以下命令
```yaml
rm -rf feeds/packages/lang/golang
git clone https://github.com/zhiern/golong feeds/packages/lang/golang
```

