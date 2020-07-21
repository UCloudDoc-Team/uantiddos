# 5. 清洗阈值调整

根据自己的业务类型，可以自助调整清洗阈值。

清洗阈值可以根据EIP所绑定的不同产品进行分别编辑，目前支持ULB/NAT网关/普通EIP三类。

如果选择了ULB的清洗阈值为30w pps，那么意味着当前的清洗阈值为：

syn:30wpps,ack:30wpps,icmp:2wpps,udp:30wpps
dns:2wpps,ssdp:2wpps,ntp:2wpps,other:2wpps

![](/images/uclean/opintro/清洗阈值.png)
