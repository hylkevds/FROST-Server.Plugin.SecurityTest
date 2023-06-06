# Fine-Grained Security Test

A fine-grained security definition for FROST-Server.

## Users, Projects, Roles, UserProjectRoles

**Users** are actors that can log in. Users are stored in the `USERS` table. Test users are:
- read
- write
- admin

The `Users` entity type is only visible to admin users.

**Roles** embody sets of permissions that a user can have. Roles are stored in the `ROLES` table. Test roles are:

- read
- create
- obsCreare
- update
- delete
- admin

The `Roles` entity type is only visible to admin users.

Users can have global Roles. The global roles are stored in the `USER_ROLES` table that directly links Users to Roles.

A global admin user is allowed to do everything. A user with a global "create" role is allowed to create all entity types except for admin-only types (Users, Roles, UserProjectRoles).

**Projects** are administrative entities grouping data (through Things). Projects are stored in the `PROJECTS` table.

Users can have project-roles. Users are linked to a Project with a certain Role through the `USER_PROJECT_ROLE` table

**UserProjectRoles** Link a User with a specific Role to a Project. A User can have multiple Roles in the same Project.

The `UserProjectRoles` entity type is only visible to admin users.
