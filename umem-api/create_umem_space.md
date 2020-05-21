# 创建内存空间 - CreateUMemSpace

## 简介

创建UMem内存空间





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUMemSpace)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUMemSpace`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Size** | int | 内存大小, 单位:GB, 范围[1\~1024] |**Yes**|
| **Name** | string | 空间名称,长度(6<=size<=63) |**Yes**|
| **Protocol** | string | 协议:memcache, redis (默认redis).注意:redis无single类型 |No|
| **Type** | string | 空间类型:single(无热备),double(热备)(默认: double) |No|
| **ChargeType** | string | Year , Month, Dynamic, Trial 默认: Month |No|
| **Quantity** | int | 购买时长 默认: 1 |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SpaceId** | string | 创建内存空间ID列表 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUMemSpace
&Region=cn-north-02
&Zone=cn-bj2-04
&Size=1
&Name=SpaceName
```

### 响应示例
    
```json
{
  "Action": "CreateUMemSpaceResponse",
  "RetCode": 0,
  "SpaceId": "umem-opqmjd"
}
```




