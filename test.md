# 视界广告小程序接口

## 目录
 #### 1.概述说明
 #### 2.接口明细

 
# 一.概述说明

描述广告小程序数据接口的详细请求和响应参数。 


## 数据验证方式
请求链接拼接uid和token，uid和token由初始登录获取

## 响应数据格式
JSON


## 其他
接口中字段长度单位均为字节，UTF8编码下 1个汉字=3个字节

 # 二.接口明细


#### 1.视界系统广告小程序项目广告订单数据接口

* 说明
    
    用于提供广告小程序相关项目订单详情及效果数据和获客数据。    

* URL

  正式：http://see.edata.leju.com/api/Addprogram/get_order_data?uid=100&token=31183de7a7b6bc3964aaab485687poiu
  
  测试：http://see.edata.bch.leju.com/api/Addprogram/get_order_data?uid=100&token=31183de7a7b6bc3964aaab485687poiuae
  
* 请求方式

  POST

* 请求参数

|参数 | 参数名 | 类型（长度范围） | 参数说明 | 是否为空 | 样例 |
|:--------|:---|:------|:------------|:------|:------|
| product | 项目名称 | string | 项目名称（多个用逗号，隔开） | 可以为空 |南沙心意华庭 , 南沙心意华庭  |
| hid | 城市楼盘组合 | string | 城市楼盘组合数据（多个用逗号，隔开） | 非空 | yn_141908,cq_137463,nanjing_86421 |


* 响应


|参数 | 参数名 | 类型（长度范围）  | 样例 |
|:---|:---|:------|:------------|
| error_code | 响应码 | int   |  错误时返回 |
| error | 响应数据 | string   | 错误时返回数据 |

* 错误 格式 样例：
```

{
  "error_code": 10001,
  "error": "系统错误",
}
```
|参数 | 参数名 | 类型（长度范围）  | 样例 |
|:---|:---|:------|:------------|
| code | 响应码 | int   |  成功时返回0 |
| entry | 响应数据 | array   | 成功时返回数据 |

* 备注 code为0时 返回以下字段

| 参数 | 参数名称 | 类型（长度范围） | 参数说明 | 
| :--: |:------:| :------------:| :-----: |
| resource_id   | 订单id | string(32) | 订单id |
| hid | 楼盘id | int(10) | 楼盘ID | 
| city | 城市 | string(32) | 城市 | 
| title | 项目名称 | string(32) | 项目名称 | 
| house_name | 楼盘名称 | string(32) | 楼盘名称 | 
| start_time | 开始时间 | string(32) | 开始时间 | 
| end_time   | 结束时间 | string(32) | 结束时间 | 
| status | 投放状态 | string(32) | 投放状态 | 
| show | 曝光量 | string(32) | 曝光量 | 
| click | 点击量 | string(32) | 点击量 | 
| click_rate | 点击率 | string(32) | 点击率 |
| hk_count | 获客总量 | string(32) | 获客总量 | 
| hk_yes_count | 昨日获客量 | string(32) | 昨日获客量 | 
| zy_count | 线索跟进量 | string(32) | 线索跟进量 | 


* 成功 格式 样例：
```
{
    "code": 0,
    "entry": [
        {
            "resource_id": "65AAD39CA510",
            "hid": "86421",
            "city": "南京",
            "title": "雅居乐滨江国际.南京",
            "house_name": "雅居乐滨江国际",
            "start_time": "2018-01-26",
            "end_time": "2018-02-02",
            "status": "已结束",
            "show": "",
            "click": "",
            "click_rate": "0%",
            "hk_count": "",
            "hk_yes_count": "",
            "zy_count": ""
        },
        {
            "resource_id": "8E26655FC3C0",
            "hid": "137463",
            "city": "重庆",
            "title": "恒大绿岛新城",
            "house_name": "恒大绿岛新城",
            "start_time": "2018-09-05",
            "end_time": "2018-10-04",
            "status": "已结束",
            "show": "",
            "click": "",
            "click_rate": "0%",
            "hk_count": 3,
            "hk_yes_count": "",
            "zy_count": ""
        },
    ]
}
```
*  错误代码说明

* 10001 -- 系统错误

* 20001 -- 验证失败

* 20002 -- 参数错误

* 20003 -- 没有数据

* 20004 -- 数据重复

* 20005 -- 添加失败

* 20102 -- 数据不存在


#### 2.视界系统广告小程序项目广告订单获客详情数据接口


* 说明
    
    用于提供广告小程序相关项目订单获客详情。    

* URL

  正式：http://see.edata.leju.com/api/Addprogram/get_hk_data?uid=100&token=31183de7a7b6bc3964aaab485687poiu
  
  测试：http://see.edata.bch.leju.com/api/Addprogram/get_hk_data?uid=100&token=31183de7a7b6bc3964aaab485687poiuae
  
* 请求方式

  POST

* 请求参数

|参数 | 参数名 | 类型（长度范围） | 参数说明 | 是否为空 | 样例 |
|:--------|:---|:------|:------------|:------|:------|
| product | 项目名称 | string | 项目名称（多个用逗号，隔开） | 可以为空 |南沙心意华庭 , 南沙心意华庭  |
| hid | 城市楼盘组合 | string | 城市楼盘组合数据（多个用逗号，隔开） | 非空 | yn_141908,cq_137463,nanjing_86421 |
| resource_id | 订单号 | string | 订单号（多个用逗号，隔开） | 可以为空 | yn_141908,cq_137463,nanjing_86421 |


* 响应


  |参数 | 参数名 | 类型（长度范围）  | 样例 |
|:---|:---|:------|:------------|
| error_code | 响应码 | int   |  错误时返回 |
| error | 响应数据 | string   | 错误时返回信息 |

* 错误 格式 样例：
```

{
  "error_code": 10001,
  "error": "系统错误",
}
```
  |参数 | 参数名 | 类型（长度范围）  | 样例 |
|:---|:---|:------|:------------|
| code | 响应码 | int   |  成功时返回0 |
| entry | 响应数据 | array   | 成功时返回数据 |

* 备注 code为0时 返回以下字段

| 参数 | 参数名称 | 类型（长度范围） | 参数说明 | 
| :--: |:------:| :------------:| :-----: |
| phone   | 手机号码 | string(32) | 手机号码隐藏中间4位，以*代替 | 
| real_name | 用户姓名 | string(32) | 用户姓名 | 
| date | 获客时间 | string(32) | 最新一条获客记录时间 | 
| product_name | 来源广告产品 | string(32) | 最新一条获客记录来源产品 | 
| house_name | 楼盘名称 | string(32) | 最新一条获客记录来源楼盘名称 | 
| zy_name | 置业顾问 | string(32) | 置业顾问 | 
| zy_status   | 跟进状态 | string(32) | 跟进状态 | 


* 成功 格式 样例：
```
{
    "code": 0,
    "entry": [
        {
            "phone": "138****6712",
            "real_name": "无",
            "date": "20181105",
            "house_name": "东旭御山湖",
            "product_name": "乐居天幕",
            "zy_name": "",
            "zy_status": "未跟进"
        },
        {
            "phone": "186****1050",
            "real_name": "无",
            "date": "20181103",
            "house_name": "东旭御山湖",
            "product_name": "乐居天幕",
            "zy_name": "",
            "zy_status": "未跟进"
        },
    ]
}
```
*  错误代码说明

* 10001 -- 系统错误

* 20001 -- 验证失败

* 20002 -- 参数错误

* 20003 -- 没有数据

* 20004 -- 数据重复

* 20005 -- 添加失败

* 20102 -- 数据不存在


#### 2.视界系统广告小程序相关项目广告订单服务报告数据接口


* 说明
    
    用于提供广告小程序相关项目广告订单服务报告。    

* URL

  正式：http://see.edata.leju.com/api/Addprogram/get_order_product_data?uid=100&token=31183de7a7b6bc3964aaab485687poiu
  
  测试：http://see.edata.bch.leju.com/api/Addprogram/get_order_product_data?uid=100&token=31183de7a7b6bc3964aaab485687poiuae
  
* 请求方式

  POST

* 请求参数

|参数 | 参数名 | 类型（长度范围） | 参数说明 | 是否为空 | 样例 |
|:--------|:---|:------|:------------|:------|:------|
| resource_id | 订单号 | string | 订单号（多个用逗号，隔开） | 非空 | yn_141908,cq_137463,nanjing_86421 |


* 响应


  |参数 | 参数名 | 类型（长度范围）  | 样例 |
|:---|:---|:------|:------------|
| error_code | 响应码 | int   |  错误时返回 |
| error | 响应数据 | string   | 错误时返回数据 |

* 错误 格式 样例：
```

{
  "error_code": 10001,
  "error": "系统错误",
}
```
  |参数 | 参数名 | 类型（长度范围）  | 样例 |
|:---|:---|:------|:------------|
| code | 响应码 | int   |  成功时返回0 |
| entry | 响应数据 | array   | 成功时返回数据 |

* 备注 code为0时 返回以下字段
* （1）订单为超级智投产品

| 参数 | 参数名称 | 类型（长度范围） | 参数说明 | 
| :--: |:------:| :------------:| :-----: |
| pic   | 楼盘图片 | string | 楼盘图片 | 
| product_crm | 产品名称 | string(32) | 产品名称 | 
| house_name | 楼盘名称 | string(32) | 楼盘名称 | 
| deliver_start_time | 投放开始时间 | string(32) | 开始时间 | 
| deliver_end_time   | 投放结束时间 | string(32) | 结束时间 | 
| status | 投放状态 | string(32) | 投放状态 | 
| hk_count | 获客总量 | int | 获客总量 | 
| thread | 线索跟进量 | string(32) | 线索跟进量 | 


* 成功 格式 样例：
```
{
    "code": 0,
    "entry": {
        "pic": "https://src.leju.com/imp/imp/deal/aa/10/b/6eda529c820885e0f4a9e50fabd_p7_mk7_cm208X156_wm47.jpg",
        "house_name": "中交中央公园",
        "product_crm": "超级智投",
        "deliver_start_time": "2018-10-22 00:00:00",
        "deliver_end_time": "2018-11-07 23:59:00",
        "status": "已结束",
        "hk_count": 165,
        "thread": ""
    }
}
```
* （2）订单为搜索通产品

| 参数 | 参数名称 | 类型（长度范围） | 参数说明 | 
| :--: |:------:| :------------:| :-----: |
| pic   | 楼盘图片 | string | 楼盘图片 | 
| product_crm | 产品名称 | string(32) | 产品名称 | 
| house_name | 楼盘名称 | string(32) | 楼盘名称 | 
| deliver_start_time | 投放开始时间 | string(32) | 开始时间 | 
| deliver_end_time   | 投放结束时间 | string(32) | 结束时间 | 
| status | 投放状态 | string(32) | 投放状态 | 
| show | 曝光总量 | string(32) | 曝光总量 | 
| click | 点击量 | string(32) | 点击量 | 
| click_rate | 点击率 | string(32) | 点击率 |
| day_data | 日效果数据 | array |  日效果数据 | 
| date | 日期 | string(32) |  投放日期 | 
| show | 曝光量 | string(32) |  日维度曝光量 | 
| click | 点击量 | string(32) |  日维度点击量 | 
| words_data | 关键词数据 | array | 关键词曝光量top10 |
| keyword | 关键词 | string(32) |  关键词 | 
| kshow | 曝光量 | string(32) |  曝光量 | 


* 成功 格式 样例：
```
{
    "code": 0,
    "entry": {
        "pic": "https://src.leju.com/imp/imp/deal/b9/d2/3/be77439423d26a7c1e1f9ab7509_p7_mk7_cm208X156_wm47.jpeg",
        "house_name": "东旭御山湖",
        "product_crm": "乐居天幕",
        "deliver_start_time": "2018-11-01 00:00:00",
        "deliver_end_time": "2018-11-30 23:59:59",
        "status": "已结束",
        "show": "73375",
        "click": "6838",
        "click_rate": "9.32 %",
        "day_data": [
            {
                "date": "20180910",
                "show": "277",
                "click": "28"
            },
            {
                "date": "20180911",
                "show": "222",
                "click": "22"
            },
            {
                "date": "20180912",
                "show": "195",
                "click": "31"
            },
            {
                "date": "20180913",
                "show": "249",
                "click": "23"
            },
        ],
        "words_data": [
            {
                "keyword": "北京首开琅樾",
                "kshow": "2"
            },
            {
                "keyword": "孙河别墅",
                "kshow": "1"
            }
        ]
    }
}
```
* （3）订单为其它广告产品

| 参数 | 参数名称 | 类型（长度范围） | 参数说明 | 
| :--: |:------:| :------------:| :-----: |
| pic   | 楼盘图片 | string | 楼盘图片 | 
| product_crm | 产品名称 | string(32) | 产品名称 | 
| house_name | 楼盘名称 | string(32) | 楼盘名称 | 
| deliver_start_time | 投放开始时间 | string(32) | 开始时间 | 
| deliver_end_time   | 投放结束时间 | string(32) | 结束时间 | 
| status | 投放状态 | string(32) | 投放状态 | 
| show | 曝光总量 | string(32) | 曝光总量 | 
| click | 点击量 | string(32) | 点击量 | 
| click_rate | 点击率 | string(32) | 点击率 |
| day_data | 日效果数据 | array |  日效果数据 | 
| date | 日期 | string(32) |  投放日期 | 
| show | 曝光量 | string(32) |  日维度曝光量 | 
| click | 点击量 | string(32) |  日维度点击量 | 


* 成功 格式 样例：
```
{
    "code": 0,
    "entry": {
        "pic": "https://src.leju.com/imp/imp/deal/71/df/7/ccd0140dc7049be055a1543a4a6_p7_mk7_cm208X156_wm47.jpeg",
        "house_name": "融创海棠湾",
        "product_crm": "开屏包",
        "deliver_start_time": "2017-12-31 00:00:00",
        "deliver_end_time": "2018-01-04 23:59:59",
        "status": "已结束",
        "show": "2969698",
        "click": "2062",
        "click_rate": "0.07 %",
        "day_data": [
            {
                "date": "20171223",
                "show": "42",
                "click": "6"
            },
            {
                "date": "20171225",
                "show": "764",
                "click": "4"
            },
            {
                "date": "20171226",
                "show": "241",
                "click": "6"
            },
            {
                "date": "20171227",
                "show": "257",
                "click": "5"
            },
        ]
    }
}
```
*  错误代码说明

* 10001 -- 系统错误

* 20001 -- 验证失败

* 20002 -- 参数错误

* 20003 -- 没有数据

* 20004 -- 数据重复

* 20005 -- 添加失败

* 20102 -- 数据不存在
