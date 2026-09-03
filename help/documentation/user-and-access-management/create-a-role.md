---
title: Create a role with Brand Concierge permission
description: Learn how to create a role and grant it the permission required to access Brand Concierge.
---

# Create a role with Brand Concierge permission

Create a role in Adobe Experience Platform Permissions to grant users access to Brand Concierge.

>[!PREREQUISITES]
>
>- You must have the administrator permissions required to manage roles and permissions.
>- The user must first be added to the Adobe Experience Platform organization. For more information, see [Add a user to the organization](./add-a-user-to-the-org.md).

## Create the role

1. Sign in to `experienceplatform.adobe.com`.

1. In the left navigation, scroll to and select **Permissions**.
1. Go to **Roles** to view existing roles, and select **Create a new role**.
1. Enter a name for the role, such as `Brand Concierge Access Users`, add a description, and confirm the creation.
1. Open the new role and assign permissions:

   1. Search the permission list for **Brand Concierge**.
   1. Select **Manage Brand Concierge**.

   At this time, **Manage Brand Concierge** is the only available Brand Concierge permission; granular permission tiers are not yet available.

1. Select the sandbox or sandboxes that the role can access.

   An organization can contain multiple sandboxes, which are isolated workspaces. Select only the sandboxes appropriate for this role.

1. Select **Save**.

## Next steps

After the role is created, add users to it. For more information, see [Add users to the Brand Concierge role](./add-a-user-to-the-role.md).
