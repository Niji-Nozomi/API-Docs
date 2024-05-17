## 接口描述

> 手机归属地查询

## 接口地址

请求方式：`GET`

返回格式：`JSON`

```API
https://api.nxvav.cn/api/tel/
```

## 请求示例

[https://api.nxvav.cn/api/tel/?tel=18888888888](https://api.nxvav.cn/api/tel/?tel=18888888888)

[https://api.nxvav.cn/api/tel/?tel=15888888888](https://api.nxvav.cn/api/tel/?tel=15888888888)

#### 使用场景

<!-- tabs:start -->

#### **html**

```html
等待编辑...
```

#### **php**

```php
<?php
// 定义头部信息
header('Access-Control-Allow-Origin:*');
header('content-type:application/json');
// API接口
$url  = 'https://api.nxvav.cn/api/tel/?tel=18888888888';

// 设置URL和相应的选项
$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
// 抓取URL并把它传递给data参数
$data = curl_exec($curl);
// 关闭cURL资源，并且释放系统资源
curl_close($curl);

// 对JSON格式的字符串进行编码
$data = json_decode(trim($data,chr(239).chr(187).chr(191)));

// 输出状态码
echo $data -> code;
// 输出手机号
echo $data -> tel;
// 输出归属地
echo $data -> local;
// 输出号码段
echo $data -> duan;
// 输出卡类型
echo $data -> type;
// 输出运营商
echo $data -> yys;
// 输出通讯标准
echo $data -> bz;
?>
```

<!-- tabs:end -->

## 请求参数

| 参数名 | 类型 | 示例 | 说明 |
| ----- | ----- | ---- | ---- |
| tel | 必填 | 手机号码 | 手机号码 |

## 返回参数

| 返回参数 | 说明 |
| ------ | ------ |
| code | 状态码 |
| tel | 手机号码 |
| local | 归属地 |
| duan | 号码段 |
| type | 卡类型 |
| yys | 运营商 |
| bz | 通信标准 |

## 状态代码

| 返回状态 | 说明 |
| ------- | ---- |
| 200 | 获取正常 |
| 202 | 无数据 |

## 返回示例

```json
{
	"code": "200",
	"tel": "18888888888",
	"local": "归属地：北京市",
	"duan": "号码段：1888888",
	"type": "卡类型：北京移动TD-SCDMA卡 (3G)",
	"yys": "运营商：中国移动",
	"bz": "通信标准：TD-SCDMA (时分同步码分多址)"
}
```