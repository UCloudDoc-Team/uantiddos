# 5. 清洗阈值调整

根据自身业务类型，可自助调整清洗阈值。

选择地域，点击详情按钮，进入详情页。

![](/images/uclean/opintro/清洗阈值调整.png)

在清洗阈值区域点击编辑按钮，进入设置页面，可根据EIP绑定的资源类型进行设置，目前有ULB/NAT网关/普通EIP三种类型。

![](/images/uclean/opintro/清洗阈值编辑.png)

比如设置ULB的清洗阈值为500Kpps，那么当前账号下的所有外网ULB的清洗阈值为：

syn:500Kpps,ack:500Kpps,icmp:20Kpps,udp:500Kpps
dns:20Kpps,ssdp:20Kpps,ntp:20Kpps,other:20Kpps

![](/images/uclean/opintro/清洗阈值设置.png)

