# 若在调整OpenWrt系统组件的过程有多次保存操作，则建议先删除.config.old文件再继续操作
rm -f .config.old

# 根据编译环境生成默认配置
make defconfig

# 对比默认配置的差异部分生成配置文件（可以理解为增量）
./scripts/diffconfig.sh > seed.config

#...
```
./scripts/feeds clean
./scripts/feeds update -a
./scripts/feeds install -a
make menuconfig
```
