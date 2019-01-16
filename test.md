# 素材库-接口文档(外部投放平台)

### 目录
 #### 1. 签名验证
 #### 2. 投放平台列表
 #### 3. 投放渠道列表
 #### 4. 投放位置列表
 #### 5. 设置标准落地页状态
 #### 6. 设置渠道落地页状态
 #### 7. 落地页楼盘列表
 #### 8. 多楼盘落地页-添加楼盘
 #### 9. 多楼盘落地页-删除投放/竞品楼盘
 #### 10. 更新标准落地页的ocpc状态
 #### 11. 素材包状态和下载地址
 
### 说明
 ##### 测试域名： 123.59.190.220 material.bch.leju.com
 ##### 线上域名： material.leju.com
 
### 接口返回
数据格式： json

接口返回成功:

字段名称 | 字段说明
---|---
code | 成功代码值为0
entry | 返回数据列表

接口返回失败：

字段名称 | 字段说明
---|---
code | 错误代码
error | 错误信息

 
### 一.签名验证

所有接口，参与加密的参数：appkey,   timestamp，加密函数如下：

请求方式: GET

    private function _create_sign() {

        $token = '123456';
        $sign_data = array(
            'appkey' => '1000000001',
            'timestamp' => time(),
        );
        ksort($sign_data);
        $temp_str = http_build_query($sign_data);
        $sign = md5($temp_str . $token);
        return $sign;
    }

### 二.投放平台列表
#### 接口地址：http://material.leju.com/api/channel/get_platform_list

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名

#### url示例：http://material.leju.com/api/channel/get_platform_list?appkey=1000000001&timestamp=1542767649&sign=a3a9739d59be9dac5c3f1ae3df4854d8

### 三.投放渠道列表
#### 接口地址：http://material.leju.com/api/channel/get_channel_list

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名

#### url示例：http://material.leju.com/api/channel/get_channel_list?appkey=1000000001&timestamp=1542767649&sign=a3a9739d59be9dac5c3f1ae3df4854d8

### 四.投放位置列表
#### 接口地址：http://material.leju.com/api/channel/get_position_list

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名

#### url示例：http://material.leju.com/api/channel/get_position_list?appkey=1000000001&timestamp=1542767649&sign=a3a9739d59be9dac5c3f1ae3df4854d8

### 五.设置标准落地页状态
#### 接口地址：http://material.leju.com/api/land_page/update_status

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名
land_page_id | 标准落地页id，支持数组和整型
status | 整型，1启用，-1禁用

#### url示例：http://material.leju.com/api/land_page/update_status?appkey=1000000001&land_page_id[]=1&land_page_id[]=2&status=-1&timestamp=1542781967&sign=c868d5070f7c1a6bcfb1fddf60d478bd

### 六.设置渠道落地页状态
#### 接口地址：http://material.leju.com/api/land_page/update_url_status

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名
land_page_url_id | 渠道落地页id，支持数组和整型
status | 整型，1启用，-1禁用

#### url示例：http://material.leju.com/api/land_page/update_url_status?appkey=1000000001&land_page_url_id[]=1&land_page_url_id[]=2&status=-1&timestamp=1542781967&sign=8d1ce8346cd23d33fc382aeade7a663c

### 七.落地页楼盘列表
#### 接口地址：http://material.leju.com/api/land_page/get_house_list

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名
land_page_id | 整型，标准落地页id

#### url示例：http://material.leju.com/api/land_page/get_house_list?appkey=1000000001&land_page_id=9&timestamp=1544237953&sign=75641a6e7568e22ee66b54c2d9671fb9

### 八.多楼盘落地页-添加楼盘
#### 接口地址：http://material.leju.com/api/land_page/add_house

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名
land_page_id | 整型，标准落地页id
user_name | B端账号
house_list | 数组，楼盘列表

house_list数组：

key名称 | key说明
---|---
hid | 整型，页面留资楼盘hid
city_en | 页面留资楼盘city_en
type | 页面留资楼盘类型, 1推广楼盘, 2竞品楼盘
belong_hid | 所属推广楼盘hid，type为2时必选
belong_city | 所属推广楼盘city_en，type为2时必选
belong_name | 所属推广楼盘名称，type为2时必选

#### url示例：http://material.leju.com/api/land_page/add_house?appkey=1000000001&timestamp=1544237953&sign=75641a6e7568e22ee66b54c2d9671fb9&land_page_id=183&user_name=liubo4&&house_list[0][hid]=140601&house_list[0][city]=cq&house_list[0][type]=1&house_list[0][belong_hid]=&house_list[0][belong_city]=&house_list[0][belong_name]=&house_list[1][hid]=150119&house_list[1][city]=cq&house_list[1][type]=1&house_list[1][belong_hid]=118788&house_list[1][belong_city]=cq&house_list[1][belong_name]=恒大云湖上郡

### 九.多楼盘落地页-删除投放/竞品楼盘
#### 接口地址：http://material.leju.com/api/land_page/delete_house

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名
land_page_id | 整型，标准落地页id
user_name | B端账号
house_list | 数组，楼盘列表

house_list数组：

key名称 | key说明
---|---
hid | 整型，页面留资楼盘hid
city_en | 页面留资楼盘city_en
type | 页面留资楼盘类型, 1推广楼盘, 2竞品楼盘

#### url示例：http://material.leju.com/api/land_page/delete_house?appkey=1000000001&timestamp=1544237953&sign=75641a6e7568e22ee66b54c2d9671fb9&land_page_id=9&user_name=liubo4&house_list[0][hid]=140601&house_list[0][city]=cq&house_list[0][type]=1&house_list[1][hid]=150119&house_list[1][city]=cq&house_list[1][type]=2

### 十.更新标准落地页的ocpc状态
#### 接口地址：http://material.leju.com/api/land_page/update_base_data

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名
land_page_id | 整型，标准落地页id
is_ocpc | 整型，1是，-1否

#### url示例：http://material.leju.com/api/land_page/update_base_data?appkey=1000000001&timestamp=1545203616&sign=7545165d39e320dc4567168dcdd096b9&land_page_id=1&is_ocpc=1

### 十一.素材包状态和下载地址
#### 接口地址：http://material.leju.com/api/material/get_download_url

GET参数：

参数名称 | 参数说明
---|---
appkey | 固定值：1000000001
timestamp | 整型，1小时以内有效
sign | 签名
land_page_id | 整型，标准落地页id

#### url示例：http://material.leju.com/api/material/get_download_url?appkey=1000000001&timestamp=1544603806&sign=6535a6ecef045c1c45e90c3db31ed715&land_page_id=1



