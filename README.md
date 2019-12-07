# KCPTUNE
安装Kcptune

安装Kcptune脚本：
wget --no-check-certificate https://github.com/kuoruan/shell-scripts/raw/master/kcptun/kcptun.sh
chmod +x ./kcptun.sh
./kcptun.sh
安装目录：/usr/local/kcptun
配置文件：/usr/local/kcptun/server-config.json
启动：
supervisorctl start kcptun
停止：
supervisorctl stop kcptun
重启：
supervisorctl restart kcptun
状态：
supervisorctl status kcptun
卸载：
./kcptun.sh uninstall

常见问题
1.SSR一键安装脚本：
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log

2.安装Kcptun过程中，如果出现提示Python版本过低：
python更新至3.6一键安装命令:
wget https://www.moerats.com/usr/shell/Python3/Debian_Python3.6.sh && sh Debian_Python3.6.sh

3.安装python安装工具pip
下载get-pip.py 文件
wget https://bootstrap.pypa.io/get-pip.py --no-check-certificate
执行安装
python get-pip.py
如果 安装完成pip 命令不能使用，搜索系统中pip文件，创建命令链接
ln -s /usr/local/python27/bin/pip  /usr/bin/pip
安装supervisord
pip install supervisor
安装后会出现两个命令
/usr/bin/supervisord -- supervisor 服务守护进程
/usr/bin/supervisorctl -- supervisor 控制台进程
测试安装是否成功
echo_supervisord_conf

4.python3.6安装成功后，会与原有的Python 2.x版本共存，此时默认的Python版本仍然是2.x。在这种情况下，Kcptun的安装仍然可能会受到影响。
执行命令后重启系统
cd /usr/bin
mv python python.backup
ln -s /usr/local/bin/python3 /usr/bin/python
