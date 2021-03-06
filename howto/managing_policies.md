# 创建和管理策略

本文指导如何管理定义特定资源的访问权限的策略。本任务是管理用户、用户组、服务账号的自定义权限的前提条件。

## 创建策略<creation>

您可以使用以下方法创建策略：

- 授予某些服务的权限
- 授予包括新添加服务在内的所有服务的完全权限。

1. 在EnOS控制台中选择 **IAM > 策略管理**。

2. 点击 **新建权限策略**。

3. 在 **基本信息** 页面中，填入该策略的基本信息，点击 **下一步**。

4. 在 **配置权限** 页面中，你可以点选服务的复选框来授权。

5. 点击 **保存** 完成创建。

## 删除策略<deletion>

删除策略时，EnOS会撤消已授予此策略的用户、用户组或服务账号的相应权限。

1. 在EnOS控制台中选择 **IAM > 策略管理**。

2. 点击需要删除的策略后的 |delete_icon| 。

3. 在弹出窗口中，点击 **确认** 完成删除。

.. |delete_icon| image:: ../media/delete_icon.png

<!--end-->
