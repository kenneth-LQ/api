# 查询房间列表及房间累计用户，峰值用户，当前用户-QueryURtcOnlineUsers

查询此appid下指定时间段内房间列表及其累计用户，峰值用户，当前用户

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|查询的AppId (不能为空)|**Yes**|
|StartTime|int|开始时间(秒时间戳）|**Yes**|
|EndTime|int|结束时间(秒时间戳）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode为0时返回succed,不为0返回具体的错误消息提示内容|**Yes**|
|Data|array|类型参见RoomUsers,具体包含房间ID和具体人数|**Yes**|

## RoomUsers
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RoomId|string|房间id|**Yes**|
|Num|int|在线人数|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcOnlineUsers
&AppId=URtc-h4r1txxy
&StartTime=1563150096
&EndTime=1563158718
```

# Response Example
```
{
    "Msg": "Succeed", 
    "Action": "QueryURtcOnlineUsersResponse", 
    "Data": [
        {
            "Num": 123, 
            "RoomId": "111"
        }
    ], 
    "RetCode": 0
}
```
