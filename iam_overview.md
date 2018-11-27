# IAM overview

EnOS Identity and Access Management (IAM) helps you manage user identities and control access to your resources in EnOS. 通过IAM，你可以创建、管理用户账户，验证账户身份（登陆），并可以控制这些账户对EnOS内资源的操作权限。当组织内存在多用户协同操作资源时，可以按需为用户分配最小权限，降低企业的信息安全风险。

EnOS applies the identity and access management (IAM) scheme to achieve multi-tenancy. In EnOS, each tenant is managed as an organizational unit.  Data that belongs to different organizations are securely segregated and can only be accessed by users that are registered to the organization.

IAM also ensures that a user can access only resources that the user is authorized to access. This is achieved through properly group users and assigning propper access permissions.

The built-in IAM schemes of EnOS provide capabilities of identity management, authentication, and authorization.

## Identity management

With IAM, a hierarchy structure is introduced to represent the relationship that exists within an organization. Each tenant is identified as an organizational unit (OU).

EnOS offer the following types of identities:
- *User accounts* are usually created for EnOS Console users and operation staff.
- *Service accounts* (a.k.a. Application tokens) are assigned to applications, for accessing the EnOS service APIs.
- *Device identities* are assigned to all devices (including edge devices) that connect to the EnOS Cloud.

All identities are created under OUs. Among the types of user identities, EnOS provides several types of user accounts, for more information, see [IAM Concepts](iam_concepts).

## Authentication

IAM provides different authentication methods for different account types.

- User accounts are authenticated through valid credentials (username and password). Strong password with required complexity is enforced by security policy managed by OU administrators. Multi-factor authentication is available as a configurable security option.

- Service accounts use access keys (i.e. digital signatures) to be authenticated by EnOS. For more information, see [Application management overview]().

- Devices and edges use X.509 certifications to establish the secure data communication tunnels with EnOS Cloud. For more information, see [Securing communication with EnOS IoT Hub](https://docs.envisioniot.com/docs/enos/en/latest/security/x509_ca/secure_communication_iothub.html).<!--Devices with TPM chips will be authenticated with its encrypted certifications stored in the hardware.-->

## Authorization

EnOS adopts Role-Based-Access-Control (RBAC) that is a policy neutral access control mechanism defined around roles and privileges. Access control rule is defined as a 3-tuples in the form of role-permission-resource. The resource includes the following:

- Applications: applications that a role has access to
- User Interface: menu items or buttons that a role can see
- API: APIs that a role can invoke<!--EnOS 1.1是否支持-->
- Data: data that a role can read or write<!--EnOS 1.1是否支持-->
- Reports: reports that a role can read<!--EnOS 1.1是否支持-->
- Events: events from an application that a role can view or handle<!--EnOS 1.1是否支持-->

IAM allows OU administrator to define access control rules to grant privileges/ permissions of resources to other accounts through the EnOS Console GUI or through the APIs.

Accounts with proper privileges granted may access the corresponding resources via EnOS service APIs or EnOS Console. Access control validation is performed by IAM service for each access attempt.

## Major functions

The identify management on EnOS involves the following dimensions:

  - Lifecycle management

  - The OU administrator can create, edit, and delete accounts that are created natively within the OU
  - The OU administrator can add and remove external users from the current OU
  - The OU administrator can add and remove users that are imported through LDAP federation, and can remove all LDAP accounts by deleting the LDAP connection

- Authorization

1. The internal, external, and LDAP users can be assigned access rights through being added into proper user groups.
2. The internal, external, and LDAP users can also be assigned individual access rights.
