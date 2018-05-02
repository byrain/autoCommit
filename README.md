# autoCommit

通过计划任务(crontab) 实现自动commit。

添加计划任务：

        crontab -e

添加代码：

        30 10 * * * cd YOUR_PATH && git pull && date>>record.txt && git commit -a -m 'git auto commit' && git push origin master

做的事情就是 在每天的10点30分时 向 record 文件写入当前的时间，并提交

查看crontab的日志记录：

    + tail -f /var/log/cron
    + tail -f /var/spool/mail/root

为crontab增加日志

    30 10 * * * $HOME/for_crontab/createTomorrowTables >> $HOME/for_crontab/mylog.log 2>&1

