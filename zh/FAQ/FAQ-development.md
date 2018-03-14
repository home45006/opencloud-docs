####  产品问题

<u>**Q：**网关设备支持连接多少个子设备？</u>

**A：**最多支持32个子设备。

<br />

<u>**Q：**空调伴侣上报机制？</u>

**A：**空调伴侣上报机制：变化值超过5W。



<u>**Q：**智能插座和墙壁插座功率上报机制？</u>

**A：**智能插座和墙壁插座功率上报机制：变化幅度超过5%且大于3W，或心跳上报（心跳周期为5-8分钟）。



<u>**Q：**温湿度传感器数据上报规则？</u>

**A：**温湿度传感器数据上报规则：1）温度：变化超过±0.5℃就上报，或跟随湿度一起上报；2）湿度：变化超过±6%就上报，或跟随温度一起上报，温湿度数据不会随心跳上报。



#### 云端开发

<u>**Q：**设备耗电量cost_energy的统计单位是什么？是什么时间的数据？</u>

**A：**空调伴侣、智能插座、暗盒插座和零火开关支持耗电量的上报，单位wh，数值表示设备第一次入网后累计的耗电量，当前耗电量不支持清零。



<u>**Q：**使用Postman测试API时出现："Could not get any response"？</u>

**A：**可能原因：1）公司网络对访问做了限制；2）Postman启用了SSL验证（SSL certifacate verification）。



<u>**Q：**设备已离线，调用API查询设备的资源值时，仍正常返回结果，返回的是什么数据？</u>

**A：**返回的数值为设备离线前最后的状态。



<u>**Q：**如何查询某个资源一天的历史数据？</u>

**A：**调用查询资源历史数据的API（/open/res/query/history/option），不设置行号，仅设置时间和资源即可。例如：

```
{
    "openId": "xxxx",
    "did": "lumi.158d0001xxxx",
    "startDate": "2018-01-19",
    "endDate": "2018-01-19",
    "option": [
        "switch_status"
    ]
}
```



#### 网关局域网开发

<u>**Q：**米家APP没有开启“局域网通信协议”功能的入口？</u>

**A：**打开APP，选择需要进行局域网通信的网关，单击页面右上角的“...”，再单击“关于”，iOS系统在此页面空白处连续点击10次即可出现；安卓系统连续点击“插件版本”10次即可出现。

