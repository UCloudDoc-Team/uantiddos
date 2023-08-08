# 封堵清洗告警回调说明

当外网IP被封堵或者清洗时都会产生相应的告警信息，您可通过配置回调来订阅这两类告警信息。

## 封堵告警回调配置
1. 在 资源监控UMon –> 消息订阅 –> 订阅管理 –> IP封堵，点击右边的设置按钮
![](/images/usecurity/IP封堵.png)
2. 在弹出的订阅设置框中勾上回调按钮，填入对应的回调地址
![](/images/usecurity/订阅设置.png)
3. 回调接口说明参考 https://docs.ucloud.cn/umon/guide/webhook 
消息内容格式如下：
```
{
    "Title": "IP封堵告警",
    "SessionId": "4356840c-661b-44e2-8449-e5674209069e",
    "TopicName": "ip_blocking",
    "TopicNameCn": "IP封堵",
    "CustomInfo": "{\"EIPId\":\"eip-mcud4xv4p38\",\"Ip\":\"x.x.x.x\",\"PeakBps\":\"2032.00\",\"ProjectId\":\"org-4g5v3v\",\"Region\":xxx,\"RegionZh\":\"迪拜\",\"Time\":\"2023-08-08 17:15:40\",\"Type\":\"StartBlocking\"}",
    "Content": "xxx(告警内容)",
    "Signature": "xxx"
}
```

    备注：
    以上字段仅供参考，以实际告警为准。
    其中PeakBps和PeakPps的单位分别为Mbps和Kpps。


##	清洗告警回调配置
1. 在 资源监控UMon –> 消息订阅 –> 订阅管理 –> IP流量清洗预警，点击右边的设置按钮
![](/images/usecurity/IP清洗.png)
2. 在弹出的订阅设置框中勾上回调按钮，填入对应的回调地址
![](/images/usecurity/订阅设置.png)
3. 回调接口说明参考 https://docs.ucloud.cn/umon/guide/webhook 
消息内容格式如下：(主要关注CustomInfo字段，其他字段以实际告警为准，其中PeakBps和PeakPps的单位分别为Mbps和Kpps) 
```
{
    "Title": "IP清洗告警",
    "SessionId": "6b54fb76-d304-4699-ac16-ae87a0b6a74b",
    "TopicName": "ip_clean_alarm",
    "TopicNameCn": "IP流量清洗告警",
    "CustomInfo": "{\"CleanType\":\"UDP_FRAG|R_CLDAP_FLOOD\",\"EIPId\":\"eip-mcud4xv4p38\",\"Ip\":\"x.x.x.x\",\"PeakBps\":\"2032.72\",\"PeakPps\":\"226.89\",\"ProjectId\":\"org-4g5v3v\",\"Region\":xxx,\"RegionZh\":\"迪拜\",\"Time\":\"2023-08-08 17:15:38\",\"Type\":\"StartClean\"}",
    "Content": " xxx(告警内容)",
    "Signature": ""
}
{
    "Title": "IP撤出清洗告警",
    "SessionId": "6b54fb76-d304-4699-ac16-ae87a0b6a74b",
    "TopicName": "ip_clean_alarm",
    "TopicNameCn": "IP流量清洗告警",
    "CustomInfo": "{\"CleanType\":\"UDP_FRAG|R_CLDAP_FLOOD\",\"EIPId\":\"eip-mcud4xv4p38\",\"Ip\":\"x.x.x.x\",\"PeakBps\":\"2032.72\",\"PeakPps\":\"226.89\",\"ProjectId\":\"org-4g5v3v\",\"Region\":xxx,\"RegionZh\":\"迪拜\",\"Time\":\"2023-08-08 17:15:38\",\"Type\":\"StopClean\"}",
    "Content": " xxx(告警内容)",
    "Signature": ""
}
```

    备注：
    以上字段仅供参考，以实际告警为准。
    其中PeakBps和PeakPps的单位分别为Mbps和Kpps。
