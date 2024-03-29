# GetMPUTaskStatus {#reference1123 .reference}

调用GetMPUTaskStatus获取任务状态。

## 请求参数 {#section_7mm_2go_osr .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|Action|String|是|操作接口名，系统规定参数，取值：GetMPUTaskStatus。|
|AppId|String|是|应用ID，创建应用后生成。|
|ChannelId|String|是|频道ID。|
|TaskId|String|是|任务ID。|

## 返回参数 {#section_6uy_hz4_svq .section}

|参数|类型|是否必选|描述|
|--|--|----|--|
|RequestId|String|是|该条任务请求Id。|
|Status|Integer|是|任务的状态id： -   0：等待channel开始。
-   1：任务运行中 。
-   2：任务已停止 。
-   3：用户停止任务。
-   4：Channel已停止。
-   5：CDN网络问题，直播停止。
-   6：直播URL问题，直播停止。

 |

## 示例 {#section_cv1_f86_3xy .section}

请求示例

``` {#codeblock_u0g_q0o_vfe}
https://rtc.aliyuncs.com?Action=GetMPUTaskStatus&AppId=xxxx&ChannelId=xxx&TaskId=xxx<公共请求参数>
```

正常返回示例

`JSON`格式

``` {#codeblock_h2m_e70_3d3 .language-json}
{
  "RequestId": "760bad53276431c499e30dc36f6b26be", 
  "Status":0
}       
```

## 特殊错误码 {#section_q68_ntl_i3f .section}

|错误ID|错误代码|描述|Http 状态码|语义|
|----|----|--|--------|--|
|0x0702000C|InternalError|The request processing has failed due to some unknown error, exception or failure.|500|内部错误。|
|0x07080002|InvalidTask.NotFound|the specified task is not existed.|404|任务不存在。|

