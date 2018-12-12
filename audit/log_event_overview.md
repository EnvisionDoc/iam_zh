## Activity Log event schema

### log的介绍

https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-activity-log-schema


### Sample code
需要问Alex要个例子：
```
{
  "userIdentity": {
    "userId": "u15420087818641",
    "userName": "db001",
    "type": "userAccount",
    "accessKey": null,
    "sessionContext": {
      "id": "IAM_S_e6huGLv6FMUW7KCNYZ28zuPML7Uwzg8d",
      "creationDate": "2018-11-20 10:04:20",
      "mfaAuthenticated": false
    }
  },
  "organizationId": "o15420087814661",
  "sourceIpAddress": "172.20.17.248",
  "eventTime": "2018-11-20 10:04:20",
  "eventId": "signInSelectOrganization15427082605511",
  "eventName": "signInSelectOrganization",
  "eventType": "consoleAction",
  "eventVersion": "V1.0",
  "resources": [
    {consoleSignIn
      "resourceId": "u15420087818641",
      "resourceName": "db001",
      "resourceType": "user"
    },
    {
      "resourceId": "o15420087814661",
      "resourceName": "db001",
      "resourceType": "organization"
    }
  ],
  "serviceName": "IAM-Service",
  "requestId": null,
  "requestParameters": "{\"sessionId\":\"IAM_S_e6huGLv6FMUW7KCNYZ28zuPML7Uwzg8d\",\"workingOrganizationId\":\"o15420087814661\",\"organizationId\":\"o15420087814661\"}",
  "apiVersion": null,
  "errorCode": null,
  "errorMsg": null
}
```


##事件结构定义

一个事件记录包含的关键字段说明。

- **userIdentity** ：请求者的身份信息。
  + type:账号类型，当前支持用户账号类型，即userAccount
  +  userId: 用户账号的ID  
  + userName:用户名  
  + sessionContext: 会话，用户通过控制台执行操作时，会触发session创建并记录该信息。<br>Session内容包括:<br>- createDate, session创建时间；<br>-
  + mfAuthentication, 用户登陆控制台时是否使用多因子认证。

- **sourceIpAddress**：发送API请求的源IP地址。如果API请求是由用户通过控制台操作触发，则记录用户浏览器端的IP地址。
- **eventId**： 描述：事件ID，审计模块产生的，事件的唯一标识。
- **eventName**：描述：事件名称，即API操作名称，具体可以参考事件列表。
- **eventTime**： 描述：API请求的发生时间（UTC格式）。
- **eventType**： 描述：发生的事件类型，如ConsoleSignIn（用户登录），ConsoleSignOut（用户登出），ApiCall（控制台或API操作）。
- **eventVersion**： 描述：操作审计事件格式的版本。
- **referencedResource**：描述：事件记录中被操作的资源。
  + resourceType: 资源类型，如Policy（策略），User（用户），Usergroup（用户组）等
  + resourceName: 资源名称，每个资源的具体名称
  + resourceId: 资源ID       

- **serviceName**： API所属服务模块，如IAM。
- **requestId**：服务处理API请求时，所产生的消息请求ID。
- **requestParameters**：描用户API请求的输入参数。
- **apiVersion**： 调用API的版本。
- **responseElements**：返回内容，如状态变更，success（成功），或failed（失败）。
- **errorCode**：处理API请求时发生错误，返回的错误码。
- **errorMessage**： 处理API请求时发生错误，返回的错误信息。

##事件列表

对于IAM服务模块，支持的服务列表如下。

| Actions                 | 描述                                                        |
| ------------------------ | ----------------------------------------------------------- |
| consoleSignIn            | 用户登陆                                                    |
| consoleSignOut           | 用户登出                                                    |
| signInSelectOrganization | 用户登陆时选择组织                                          |
| createUser               | 创建用户                                                    |
| deleteUser               | 删除用户                                                    |
| resetUserPassword        | 管理员重置用户密码                                          |
| modifyUserPassword       | 用户修改密码                                                |
| retrieveUserPassword     | 用户找回密码                                                |
| setUserAccountStatus     | 管理员设置用户账号状态，包括enable（启用），disable（停用） |
| addExternalUser          | 添加外部用户                                                |
| removeExternalUser       | 移出外部用户                                                |
| createGroup              | 创建用户组                                                  |
| deleteGroup              | 删除用户组                                                  |
| addUserToGroup           | 添加用户至用户组                                            |
| removeUserFromGroup      | 将用户从用户组移出                                          |
| createPolicy             | 创建策略                                                    |
| deletePolicy             | 删除策略                                                    |
| appendResource           | 授权策略绑定资源                                            |
| revokeResource           | 授权策略取消策略绑定                                        |
| grantPolicy              | 授权策略                                                    |
| removePolicy             | 移除授权策略                                                |
