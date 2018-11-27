# 概念

该文章介绍了IAM中用到的主要概念，帮助您正确理解和使用IAM。

## 组织

组织在IAM中是最顶层的管理单元，是一组用户账户、资源等的集合。EnOS系统按组织进行资源隔离。您可以通过IAM功能集中查看和管理组织内的所有账户。一个组织只有一个主账户（即组织所有者）和多个其他用户账户。可以通过为其他用户账户绑定授权策略的方式，控制其对组织内资源的操作权限。

## 用户

IAM允许在一个组织内创建多个用户账户。这类用户账户有确定的身份ID和身份凭证（登录密码），可以通过控制台登录，并通过使用EnOS产品，功能，或服务，对资源进行操作。用户账户可分为

- **组织所有者**（主账户）
在EnOS系统内新建组织时，会创建一个用于登录EnOS的主账户，即组织所有者账户。该组织可使用此主账户登录控制台，通过IAM功能模块创建其他用户账户并为其授权。主账户有对当前组织下所有资源的操作和控制权限。

- **管理员账户**
主账户登录控制台后，在IAM中可以为其他用户账户授予“管理员策略”权限。管理员账户拥有组织下所有资源的操作及控制权限，包括对IAM功能的获取权限。管理员账户通过访问IAM，可管理除主账户之外的其他账户的生命周期及授权。每个管理员账户都有自己的密码以用于访问EnOS管理控制台。

- **普通账户**
组织所有者或管理员账户登录控制台后，在IAM中可以创建授权策略，然后按需创建普通用户和为普通用户分配除“管理员策略”外的最小权限。每个普通账户都有自己的密码以用于访问EnOS管理控制台。在一个组织内，可以通过三种方式添加用户账户：
  - **Ordinary user**: An ordinary user is created natively within a certain organization. The user can be authorized through being added into user groups, or assigned permissions directly.
  - **External user**: An external user, in the opposite, is created in other organizations. For example, you can add an operation staff, who is created in another organization, into your current organization.
  - **LDAP user**：LDAP users are imported through LDAP ferdatation. 可以被授予的权利是xxxx.

On top of all accounts, there is a special account that is unique in an organization, the organization administrator. <!-- which 在购买产品时向远景购买。-->


## 用户组

用户组是一组用户账户的集合，通过用户组，你可以集中管理拥有相同权限的用户账户。为用户组指定的权限策略，将同时被授予该用户组内的所有用户账户。在用户组中，你可以添加当前组织内创建的用户账户，其他组织内创建的用户账户，或添加通过LDAP服务导入的用户账号。创建用户组时，可根据不同的场景，授予不同的策略，具体请参考[最佳实践](best_practice)。

## 策略

策略定义了对EnOS内资源（平台服务、工具或资产数据等）的操作权限。策略需要被关联至用户或用户组以发生效用。针对不同的用户账号，你可以根据EnOS支持的授权颗粒度按需为用户或用户组授予不同的策略。
- 平台服务、工具：支持按菜单粒度的授权。
- 资产数据：支持授予全部资产的数据访问权限。

## 多因子认证（MFA）

Multi-Factor Authentication（MFA），是一种简单有效的最佳安全实践，它能够在用户名和密码之外再增加一层安全保护。这些多重要素结合起来将为您的账户提供更高的安全保护。启用 MFA 后，用户登录EnOS时，系统将要求输入两层安全要素：
- 第一安全要素：用户名和密码。
- 第二安全要素：通过短信或邮件接收到的可变验证码。
