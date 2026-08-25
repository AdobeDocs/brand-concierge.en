---
title: Create a role with Brand Concierge permission
description: Learn how to create a role and grant it the permission required to access Brand Concierge.
---

# Create a role with Brand Concierge permission

Create a role in Adobe Experience Platform Permissions to grant users access to Brand Concierge.

## Prerequisites

* You must have the administrator permissions required to manage roles and permissions.
* The user must first be added to the Adobe Experience Platform organization. For more information, see 'Add a user to the organization' (LINK).

## Create the role

1. Sign in to `experienceplatform.adobe.com`.

   >[!NOTE]
   >
   >Confirm the production URL with engineering before publishing this procedure. The source recording used an informal or possibly mis-transcribed URL.

2. In the left navigation, scroll to and select **Permissions**.
3. Select **Roles** to view existing roles, then select **Create a new role**.
4. Enter a name for the role, such as `Brand Concierge Access Users`, add a description, and confirm the creation.
5. Open the new role and assign permissions:

   1. Search the permission list for **Brand Concierge**.
   2. Select **Manage Brand Concierge**.

   Currently, **Manage Brand Concierge** is the only available Brand Concierge permission. Granular permission tiers are not currently available.

6. Select the sandbox or sandboxes that the role can access.

   An organization can contain multiple sandboxes, which are isolated workspaces. Select only the sandboxes appropriate for this role.

7. Select **Save**.

## Next steps

After the role is created, add users to it. For more information, see 'Add users to the role' (LINK).

## Related considerations

* The process for creating and managing sandboxes is outside the scope of this procedure.
* Confirm whether additional granular Brand Concierge permissions are planned before defining a long-term role model.
