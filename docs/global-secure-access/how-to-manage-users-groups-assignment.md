---
title: How to assign users and groups to traffic forwarding profiles
description: Learn how to assign users and groups to traffic forwarding profiles Global Secure Access (preview).
author: kenwith
ms.author: kenwith
manager: amycolannino
ms.topic: how-to
ms.date: 05/16/2024
ms.service: global-secure-access
---
# How to assign users and groups to traffic forwarding profiles

Assign specific users and groups to a traffic forwarding profile. User or group assignment limits the scope of the traffic forwarding profile so you have a mechanism to roll out the profile safely and at a controlled pace.

## Assign to specific users or user groups 
To scope the traffic profile to a specific user or group:

1. Select the **View** link next to **0 Users, 0 Groups assigned**.
1. Select the link **0 Users, 0 Groups assigned** to select specific users or groups.
1. Select **Add user/group**.
1. Select a user or group for the traffic forwarding profile and then select **Assign**.

> [!NOTE]
> If the traffic profile is disabled then, when you enable it, you see that there are zero users and zero groups assigned. This default behavior lets you slowly roll out the feature in a controlled manner.

## Assign to all users 
To scope the traffic profile to all users:

1. Select the **View** link next to **0 Users, 0 Groups assigned**.
2. Select the toggle to assign the traffic profile to all users.
3. Select **Done**.

## Revert all users assignment
You can revert the assignment of all users to a traffic profile. When you toggle off the assignment for all users, you revert to the users and groups that were assigned when you toggled it on.

To revert the traffic profile for all users:
1. Select the **View** link next to **All users assigned**.
2. Select the toggle to turn off the assignment for all users.
3. Select **Done**. 

## Automatic assignment using user attributes 

You can create and assign a dynamic group of users based on user attributes. You use dynamic groups to automatically assign users who satisfy the criteria to the profile. To learn more about automatic assignment using user attributes, see [Create or update a dynamic group in Microsoft Entra ID](../identity/users/groups-create-rule.md).

## Notes on user identity

Profiles are fetched on behalf of the Microsoft Entra user logged into the device​, not the user logged into the client​. 

If there's no Microsoft Entra user logged in, then the profile is fetched only if assigned to all users. For example, if you're logged into the device as a local admin.

Multiple users logging into the same device simultaneously isn't supported. 

## Notes on group assignment

Group-based assignment is supported for Security groups and Microsoft 365 groups whose `SecurityEnabled` setting is set to `True`.

Nested group memberships aren't supported. A user must be a direct member of the group assigned to the profile. 

## Next steps
- [Learn about Global Secure Access clients](concept-clients.md)
