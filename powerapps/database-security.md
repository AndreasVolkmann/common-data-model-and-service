<properties
	pageTitle="Configure database security"
	description="Configure database security"
	services="powerapps"
	documentationCenter="na"
	authors="maertenm"
	manager="kfend"
	editor=""
	tags=""/>

<tags
   ms.service="powerapps"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="12/06/2016"
   ms.author="kfend"/>

# Configure database security #

The Common Data Service uses a role-based security model to secure access to the database. This topic shows you how to create the security artifacts that you need to secure an app. These user roles control runtime access to data and are separate from the Environment roles that govern the Environment Administrators and Environment Makers. For an overview of environments, see [Environments overview](environments-overview.md).

It's important to understand what level of access to these entities is needed by users of the app. The Common Data Service supports the create, read, update, and delete (CRUD) permissions on entities.

- Create - Allows a user to create new entries in the entity.
- Read - Allows a user to view and search existing entries in the entity.
- Update - Allows a user to update or edit an existing entry in the entity.
- Delete - Allows a user to delete or remove an existing entry in the entity.

The two most common permissions that are used are read-only and full access. The Common Data Service comes with permissions sets for all its entities at these two permission levels. View permission sets provide read access to the entity. Maintain  permission sets provide full access to the entity.

The security model supports any combination of these permissions to be assigned to a user role. Roles combine the permissions granted across the permission sets added to them. In this way, members of a role can access all the data provided to them by the permission sets included in the role. For more information about the Common Data Service security model, see [Security model](https://docs.microsoft.com/en-us/common-data-service/entity-reference/security-model).

## Identify the entities ##
To configure the proper access controls for an app, you will need to know what entities it is using. To see the entities an app uses:

1. Open the app in PowerApps Studio.
1. Click or tap the **Content** tab.
1. Click or tap **Data sources**. The list of data sources will be displayed in the right pane.

## Configure security ##
When you create a new entity, you also need to create a new permission set or edit an existing permission set to provide access to its data. When you create an app, we recommend that you also create a permission set that provides access to all the entities needed to run the app. Security is managed in the admin center.

1. Open the [admin center](https://admin.powerapps.com).
1. Click or tap the environment that contains your database.
1. Click or tap **Security**. The **User roles** and **Permission sets** tabs are used to configure security on your database.

## Create a permission set ##
To enable access to a new app you first need to create a new permission set.

1. Click or tap **Permission sets**.
1. Click or tap **New permission set** to create a permission set.
1. Give your permission set a name and a description, and then tap or click **Create**. Your newly created permission set will now show in the list of permission sets.
1. Click or tap the permission set that you created.
1. Click or tap the **Entities** tab. The **Entities** tab contains a list of all the entities in your database. For each entity used in your app, check the permission that you want to allow.
1. Click or tap **Save**.

## Create a policy (Technical Preview) ##
To enable restrict access to the records within an entity you first need to create a policy.
1.	Click or tap **Policies**.
2.	Click or tap **New policy**.
3.	Enter a name for the policy.
4.	Enter a description of the policy.
5.	Select the type of policy to create.  If a picklist policy, enter the picklist to be used.
6.	Select the operator to be used.
7.	Select the value for the policy to check against.
8.	Click or tap **Create**.

## Assign a policy (Technical Preview) ##
To apply a policy, you must assign it to a data entity within a permission set.
1.	Click or tap **Permission Sets**.
2.	Click or tap the permission set you want to assign a policy under.
3.	Click or tap the edit button for the entity you would like to assign a policy to.
4.	Expand the Policy assignment section.
5.	Select the data operations you would like to apply a policy to (Create, Read, Update, Delete).
6.	Select the entity field the policy will be based on.
7.	Select the policy to you wish to assign.
8.	Click or tap **Assign**.
9.	Click or tap **Save**.


## Create and assign a role ##
After the proper permissions are included in a permission set, you can create a role that can be assigned to users.

1. Click or tap **User roles**.
1. Click or tap **New role**.
1. Give the role a name and description, and then click or tap **Create**. Your newly created role will now appear in the User roles list.
1. Click or tap the role that you created.
1. Click or tap the **Permission sets** tab.
1. Enter the name of the permission set that you created. A drop-down list appears as you type. Click or tap the permission set to add it to the role. Add all the permission sets that you want for the role.
1. Click or tap the **Users** tab for the role.
1. Enter the name or email addresses of the users or groups you want to add. A drop-down list appears as you type. Click or tap the user in the list. Users and groups who will have the role assigned are added to the list.
1. Click or tap **Save**.

The users or groups in this role can now access the data that is granted by any permission set associated with the role. To use the data in your database a user must have a security role and access to a PowerApp that uses the data.

## Edit permission sets and roles ##
Roles and permission sets can be edited after creation by clicking the edit icon.

To delete a role or permission set, use the delete icon.

## Out-of-the-box security roles ##
Two security roles are provided out of the box:

- Database Owner - The Database owner role is intended for users in an administrative function. The creator of the environment will automatically be added to this role. Users in this role will always have full access to all entities in the database, even as new entities are added. The Database Owner role also provides users the ability to create and edit entity schema in the database. You do not need to add permission sets to this role, only assign users to it.
- Organization User - The Organization User role is the default role assigned to all users. This role is intended to provide all users access to the entities that contain public data. If an app is shared in restricted mode, then entities it uses should be contained within this role. You do not need to assign this role, everyone in your organization already has it. You only need to add the permission sets that you wish to give to your entire organization.
