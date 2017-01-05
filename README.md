# 爬取高德地图地址库脚本

## 脚本说明
在运行该python脚本之前，需要创建在mysql中创建`地址库表`。  
服务列表包括
* 连接mysql数据库
* http请求高德地图，获取省、市、区和街道数据，两种请求条件
   1. 输入**中国**，返回`省份`数据
   2. 输入**省份**，返回`市、区`数据
   3. 输入**区**，  返回`街道`数据
* `json`数据转换为`结构化`数据
* 结构化数据存储在地址库中
存储的数据包括`经纬度`

运行的脚本格式，如下所示:
```python
python address_new.py
```
因为爬取高德地图，不能一次爬取太多数据，所以执行过程中，脚本会提示:
* `"从第几页开始？offset="` 
* `"每页多少条数据？, 默认每页1000条。limit="` 
## 地址库表结构
table文件说明：
* 创建地址库`syt_address`
* 创建省份表`provinces`
* 创建城市表`cities`
* 创建区/县表`districts`
* 创建街道表`streets`
## 日志说明
含有两个日志文件格式举例`china.log`和`city.log`