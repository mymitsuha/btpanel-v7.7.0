# btpanel-v7.7.0
btpanel-v7.7.0-backup  官方原版v7.7.0版本面板备份

**Centos/Ubuntu/Debian安装命令 独立运行环境（py3.7）**

```Bash
curl -sSO https://raw.githubusercontent.com/mymitsuha/btpanel-v7.7.0/main/install/install_panel.sh && bash install_panel.sh
```
```remove bind
rm -f /www/server/panel/data/bind.pl
```
``` remove alert
sed -i "s|bind_user == 'True'|bind_user == 'XXXX'|" /www/server/panel/BTPanel/static/js/index.js
```
