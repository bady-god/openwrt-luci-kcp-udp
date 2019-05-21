# openwrt-luci-kcp-udp

### OpenWRT-18.06.2 X64 �̼���SDK ���ص�ַ���ļ���
https://downloads.openwrt.org/releases/18.06.2/targets/x86/64/
- openwrt-18.06.2-x86-64-combined-squashfs.img.gz
- openwrt-sdk-18.06.2-x86-64_gcc-7.3.0_musl.Linux-x86_64.tar.xz

### OpenWRT-18.06.2 x86 �̼���SDK ���ص�ַ���ļ���
https://downloads.openwrt.org/releases/18.06.2/targets/x86/generic/
- openwrt-18.06.2-x86-generic-combined-squashfs.img.gz
- openwrt-sdk-18.06.2-x86-generic_gcc-7.3.0_musl.Linux-x86_64.tar.xz

### ��CPUѡ������SDK����VPS�� ��ѹSDK��������Ϊ opensdk
	tar xvJf openwrt-sdk-18.06.2-x86-64_gcc-7.3.0_musl.Linux-x86_64.tar.xz
	mv openwrt-sdk-18.06.2-x86-64_gcc-7.3.0_musl.Linux-x86_64 opensdk

### ��װ���뻷��

```
apt -y install subversion build-essential libncurses5-dev zlib1g-dev gawk git ccache gettext libssl-dev xsltproc wget unzip python time
apt -y install libcloog-isl-dev
ln -s /usr/lib/x86_64-linux-gnu/libisl.so /usr/lib/libisl.so.10
```

### ���� openwrt-luci-kcp-udp �� opensdk/package
	cd opensdk && git clone https://github.com/hongwenjun/openwrt-luci-kcp-udp.git
	mv openwrt-luci-kcp-udp/* package

### ����make menuconfig; �ڵ����Ľ�Ŀ����Luci��>3. applications����ѡΪM���ɣ������˳���
	cd opensdk && make menuconfig

### ʹ��������� luci-udptools  luci-kcptools(Ŀǰ��û�������)
```
make package/luci-udptools/compile V=99
make package/luci-kcptools/compile V=99
make package/udp2raw/compile V=99
make package/udpspeeder/compile V=99

```
- �ο��ļ�: ����openwrt��udpspeeder��udp2raw [��������](https://www.atrandys.com/2018/1255.html)
