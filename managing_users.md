# Managing users
This topic instructs how to manage and authorize user in EnoS IAM.

## Creating and authorizing an internal user
This topic instructs how to create and authorize an internal user in EnoS IAM.

### Step 1: Creating an internal user
1. In the navigation panel, click **IAM>User**.
2. In **Internal User** tab, Click **New User**.
3. In **Basic Information** step, fill in the basic information of the new user and click **Next**.
   - **Send By**: You can choose to send the password to the owner of the user account via phone or email. You also can sent the password in other safety way, such as,  .

### Step 2: Grant permission
You can assign permission for a user in the following approaches:
- Granting policies
- Assigning user to user groups. In this approach, the user will inherit all permissions that are assigned to the user groups.

To grant policies:
  1. In **Policies** tab, click **Grant Permissions**.
  2. In the pop-up window, select policies to be assigned to this user and click **Save**.
  3. Click **Save** to create the user.

To assign user to groups:
 1. In **Assign User to Group** tab, click **Assign to User Group**.
 2. In the pop-up window, select User group to be assigned to this user and click **Save**.
 2. Click **Save** to create the user.

<!--可能会被移到gettingstarted里-->


## Adding and authorizing an external user
This topic instructs how to add and authorize an external user in EnoS IAM.

### Step 1: Import an external user
1. In the navigation panel, click **IAM>User**.
2. In **External User** tab, Click **Import User**.
3. In the pop-up windows, enter the full username of the external user. If the name is correct, the detailed information will display in the dialog. Then click **Confirm**.
4. Click **Next**.

### Step 2: Grant permission
You can assign permission for a user in the following approaches:
- Granting policies
- Assigning user to user groups. In this approach, the user will inherit all permissions that are assigned to the user groups.

To grant policies:
  1. In **Policies** tab, click **Grant Permissions**.
  2. In the pop-up window, select policies to be assigned to this user and click **Save**.
  3. Click **Save** to import the user.

To assign user to groups:
 1. In **Assign User to Group** tab, click **Assign to User Group**.
 2. In the pop-up window, select User group to be assigned to this user and click **Save**.
 2. Click **Save** to import the user.





## Deleting an internal user
Delete an internal user means that this user account is completely deleted from the EnOS Cloud.

1. In the navigation panel, click **IAM>User**.
2. In **Internal User** tab, click ![Image](media/delete_icon.png) after the user to be deleted.
3. In the pop-up window, click **Confirm** to delete this user account complete.

## Remove an external user
Remove an external user means that this user is removed from the current organization.  

1. In the navigation panel, click **IAM>User**.
2. In **External User** tab, click ![Image](media/delete_icon.png) after the user to be deleted.
3. In the pop-up window, click **Confirm** to remove this user.


## Resetting password

1. In the navigation panel, click **IAM>User**.
2. In **Internal User** tab, click ![Image](media/edit_icon.png) after the user to be reset password.
3. In **Edit User Information** page, click **Reset** next to the password. System will generate a new password which shows next to the  **Reset**.
4. Remember this password and click **Save** to reset the password.


## Enabling/Disabling user account

1. In the navigation panel, click **IAM>User**.
2. In **Internal User** tab, click ![Image](media/edit_icon.png) after the user to be enabled/disabled password.
3. click **Save** to enable/disable the user account.
