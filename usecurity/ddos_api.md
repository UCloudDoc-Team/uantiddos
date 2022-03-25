# 封堵清洗告警回调说明
## 封堵告警回调配置
1. 在 资源监控UMon –> 消息订阅 –> 订阅管理 –> IP封堵，点击右边的设置按钮
![](/images/usecurity/IP封堵.png)
2. 在弹出的订阅设置框中勾上回调按钮，填入对应的回调地址
![](/images/usecurity/订阅设置.png)
3. 回调接口说明参考 https://docs.ucloud.cn/umon/guide/webhook 
消息内容格式如下：（其中PeakBps和PeakPps的单位分别为Mbps和Mpps）
```
{
    "Title": "IP封堵告警",
    "SessionId": "e8d316d5-056e-41fd-8d85-2a21c2bf18d0",
    "Signature": "xxx",
    "TopicName": "ip_blocking",
    "TopicNameCh": "IP封堵",
    "CustomInfo": {
        "EIPId": "eip-hvs0msoxxx",
        "Ip": "x.x.x.x",
        "PeakBps": "2015.00",
        "ProjectId": "org-0lo0xxx",
        "Region": xxx,
        "RegionZh": "迪拜",
        "Time": "2022-03-22 17:25:37",
        "Type": "StartBlocking"
    },
    "Content": "xxx(告警内容)"
}
```

##	清洗告警回调配置
1. 在 资源监控UMon –> 消息订阅 –> 订阅管理 –> IP流量清洗预警，点击右边的设置按钮
![](/images/usecurity/IP清洗.png)
2. 在弹出的订阅设置框中勾上回调按钮，填入对应的回调地址
![](/images/usecurity/订阅设置.png)
3. 回调接口说明参考 https://docs.ucloud.cn/umon/guide/webhook 
消息内容格式如下： 
```
{
    "Title": "IP清洗告警",
    "SessionId": "e8d316d5-056e-41fd-8d85-2a21c2bf18d0",
    "Signature": "xxx",
    "TopicName": "ip_clean_alarm",
    "TopicNameCh": "IP流量清洗告警",
    "CustomInfo": {
        "CleanType": "IP_TOTAL_OVER_THRESH",
        "EIPId": "eip-hvs0xxx",
        "Ip": "x.x.x.x",
        "PeakBps": "1228.38",
        "PeakPps": "142.32",
        "ProjectId": "org-0loxxx",
        "Region": 123,
        "RegionZh": "迪拜",
        "Time": "2022-03-22 17:39:59",
        "Type": "StartClean"
    },
    "Content": "xxx(告警内容)"
}
{
    "Title": "IP撤出清洗告警",
    "SessionId": "e8d316d5-056e-41fd-8d85-2a21c2bf18d0",
    "Signature": "xxx",
    "TopicName": "ip_clean_alarm",
    "TopicNameCh": "IP流量清洗告警",
    "CustomInfo": {
        "EIPId": "eip-hvs0xxx",
        "Ip": "x.x.x.x",
        "ProjectId": "org-0loxxx",
        "Region": 123,
        "RegionZh": "迪拜",
        "Time": "2022-03-22 17:39:59",
        "Type": "StopClean"
    }
}
```
