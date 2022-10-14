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
``` remove backdoor
#将脚本文件清空
echo "" > /www/server/panel/script/site_task.py

#脚本文件添加写保护，防止内容被写回（即使是root，不取消保护也无法写入）
chattr +i /www/server/panel/script/site_task.py
#清空所有统计日志
rm -rf /www/server/panel/logs/request/*
#为request文件夹添加写保护，防止内容写入
chattr +i -R /www/server/panel/logs/request
```
