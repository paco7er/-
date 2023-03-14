# ccurent
一个电流控制模块，对电流进行修改且去除mi_thermald的模块。（仅对K50ultra进行过测试，效果较好，其他机型自测）
#
## 主要原理
默认电流控制规则为，40度以下13A，40到44度电流用一个二次函数来拟合，44度到46度7.5A，46到49度用一个二次函数拟合，49度以上0A。
电流写入日志文件为/data/adb/modules/charge/log.txt，查看当前写入状态。
![F554B200AC54C64FB75E1F12BFFDE404](https://user-images.githubusercontent.com/86546035/224915630-2793d2f3-3ee1-4c3b-818a-63096a54b2fe.jpg)
![9E04FD32509AA3A43008004AC0896A03](https://user-images.githubusercontent.com/86546035/224915650-bd27ad0e-8f0d-42a2-9777-0ad0e789bb19.jpg)
