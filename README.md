# ccurent
一个充电电流控制模块，对充电电流进行修改且去除mi_thermal文件的模块。 

（测试机型：K50ultra、k60pro，理论可行机型：miui-120W（非120W需要修改电流参数））
#
## 主要原理
控制充电电流，实现充电电流的合理陡降和缓降。

带日志版本：充电电流实时大小写入日志文件为 sdcard/Android/paco/charge/log.txt中，便于查看当前写入状态。

配置文件：sdcard/Android/paco/charge/charge.conf。用于切换电流放置方案。
#

## 电流放置方案
### 14A方案：1

充电电流控制规则为：40度以下14A，40到44度充电电流用二次函数拟合，44度到46度维持7.5A，46到49度用二次函数拟合，49度以上0A。

![image](https://github.com/paco7er/ccurrent/assets/86546035/91cdd989-bab0-408b-8ef7-4a5312e370c8)
![image](https://github.com/paco7er/ccurrent/assets/86546035/70e3f4a0-f4b3-4241-8527-3cc5baf7ea4a)

### 21A方案：2

充电电流控制规则为：40度以下21A，40到45度充电电流用二次函数拟合，45到49度充电电流用二次函数拟合，49度以上0A。

![image](https://github.com/paco7er/ccurrent/assets/86546035/76e0a48b-b386-4caf-b4f3-da264a92059d)
![image](https://github.com/paco7er/ccurrent/assets/86546035/ad2b1bf9-de45-4fc2-938d-a0277a20dec9)

### 自定义方案：3
自己输入一个电流，单位A，充电电流保持这个值恒定。
