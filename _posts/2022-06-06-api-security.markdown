---
layout: post
title: "Securing your API's "
date: 2022-03-12 13:01:20 +0300
description: "Securing your API's" # Add post description (optional)
img:  software.jpg # Add image post (optional)(optional)
categories: [API Security]
icon: blogging.png
---
### Securing Your API's


#### REST Security Design Principles:
- **Least Privilege**: Permissions can be added as needed and should be revoked when no longer in use, per entity. Should only have required set of permissions to perform the actions for which they are authorised to perform.
- **Fail-Safe Defaults**: A user’s default access level to any resource in the system should be “denied” unless they’ve been granted a “permit” explicitly.
- **The economy of Mechanism**: The design should be as simple as possible. All the component interfaces and the interactions between them should be simple enough to understand.
- **Complete Mediation**: A system should validate access rights to all its resources to ensure that they’re allowed and should not rely on the cached permission matrix. If the access level to a given resource is being revoked, but that isn’t reflected in the permission matrix, it would violate the security.
- **Least Common Mechanism**: It concerns the risk of sharing state among different components. If one can corrupt the shared state, it can then corrupt all the other components that depend on it.
- **Psychological Acceptability**: It states that security mechanisms should not make the resource more difficult to access than if the security mechanisms were not present. In short, security should not make worse the user experience.