# 策略，角色，与权限

策略是一组对EnOS中资源（例如服务，功能和数据）的操作权限的集合。你通过为用户，用户组，或应用赋予访问策略以管理其在EnOS内可访问的资源。策略仅在分配给用用户，用户组，或应用时生效。你可以根据EnOS支持的授权颗粒度按需为用户或用户组授予不同的策略。

- EnOS服务和工具：支持菜单级授权。
- 资产及数据：支持授予组织内全部资产的数据访问权限。

IAM中的权限策略分为两类：_系统内置策略_和_自定义策略_。


## 系统内置策略

预先为EnOS内某种典型用户角色或服务账号定义的一组访问权限的结合，不可被编辑和删除。如被赋予“模型管理者”角色的用户或服务账号对其所属组织的模型有创建、删除、编辑、导入、导出、查看、实例化的读写权限。

当前EnOS提供以下内置策略：

.. csv-table::
   :widths: auto

   "角色", "权限"
   "组织管理员 Administrator", "拥有该OU所有资源的访问和管理权限"
   "安全审计员 Security Auditor", "拥有OU所有安全设置、审计日志的查看权限"
   "模型管理者 Model Administrator", "对OU的模型有创建、删除、编辑、导入、导出、查看、实例化的读写权限。包括系统管理员、管理模型的行业专家、负责模型部署的运维人员等"
   "模型使用者 Model User", "对组织下的模型有查看、导出、实例化的只读权限。包括普通用户、实施人员等"
   "资产树管理员 AssetTreeAdministrator", "对组织下的资产树有创建、删除、编辑、查看的读写权限。包括系统管理员、资产管理员、资产实施人员等"
   "资产树普通用户 Asset Tree User", "对组织下的资产树有查看的只读权限。包括普通用户、应用开发者等"
   "接入配置管理员 Connectivity Provisioning Administrator", "对组织下的设备接入配置有创建、删除、编辑、查看的读写权限。包括系统管理员、资产管理员、资产实施人员等"
   "接入配置普通用户 ConnectivityProvisioningUser", "对组织下的设备接入配置有查看的只读权限。包括普通用户、应用开发者等"

## 自定义策略

自定义策略是由根据用户或服务账号（SA）对访问EnOS服务的需要自定义的权限策略。如，当用户或服务账号只需要查询模型，则可为用户或服务账号赋予“模型管理服务”的“只读”权限。

目前EnOS支持对以下服务的自定义权限：

.. csv-table::
   :widths: auto

   "服务名称", "资源", "权限选项"
   "接入配置管理", "接入配置", "- Full Access，
    - Read Only"
   "资产树管理（控制台界面）", "EnOS控制台中的资产树", "- Full Access，
    - Read Only"
   "模型管理", "模型", "- Full Access，
    - Read Only"
   "资产树数据服务（设备数据）", "资产树节点绑定设备的数据", "- Read，
    - Control，
    - Write"

注：
- Full Access：即可对对象进行创建、删除、编辑、查看操作的读写权限
- Read Only：即对对象只能进行查看的只读权限。


  对资产树数据的操作权限有如下几种：
  - Read：即对资产只能进行查看的只读权限。
  - Control: 即对资产有下发控制指令的权利。
  - Write：对资产的属性有改动的权限。
