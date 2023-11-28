---
title: "Cloud variables"
---

# Cloud Variables

Cloud Variables are variables that persist across worlds.  
They rely on paths and user/group ownership.

Cloud Variables have two parts:

- Definition - Meta config of the variable; name, type, permissions, default
- Values - Actual value, stored per-user

${toc}

## Default values

There is some defaults to keep in mind when working with Cloud Variables:

- If no default for the variable is given, the value returned is the one for [this the type of the variable in C#](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/default-values)
- Read/Write permissions will default on `variable_owner`
- List permission will default on `variable_owner`

## Working with Cloud Variables

### Definition

To define a Cloud Variable, you will need some information such as:

- A path/name; for instance `foo.bar`
- A type (bool, string:<maxlength; maximum is 8192; default is 256>, float, floatq, doubleq, color, datetime, timespan, short, int, uint, long, ulong, byte, double, decimal)
- [Permissions](#permissions)
- A default (optional)

You can register Cloud Variables on both users and groups. Using a group has the advantage of having higher limits (8192 for a group vs 256 for a user) and additional permissions.

Creating Cloud Variables is actually really easy through commands sent to the Resonite Bot:

#### Users

- `/createUserVar <path>` - Creates a Cloud Variable with the given path
- `/setUserVarType <path> <type>` - Sets the type of the variable
- `/setUserVarDefaultValue <path> <value>` - Sets the default value of the variable
- `/setUserVarPerms <path> <action> <permission>` - Sets the [permissions](#permissions) of the variable

It is possible to do everything in one go using `/createUserVar <path> <type> <default> <read perms> <write perms> <list perms>`.

#### Groups

- `/createGroupVar <path>` - Creates a Cloud Variable with the given path
- `/setGroupVarType <path> <type>` - Sets the type of the variable
- `/setGroupVarDefaultValue <path> <value>` - Sets the default value of the variable
- `/setGroupVarPerms <path> <action> <permission>` - Sets the [permissions](#permissions) of the variable

It is possible to do everything in one go using `/createGroupVar <path> <type> <default> <read perms> <write perms> <list perms>`.

### Permissions

#### Action

| Action | Description                       |
| ------ | --------------------------------- |
| read   | Read values of a cloud variable   |
| write  | Writes values of a cloud variable |
| list   | List all the values of a variable |
| all    | All the permissions above         |

#### Group/Type permissions

##### Common

| Type                         | Description                                                                                  | Locations              | Limitations                                                              |
| ---------------------------- | -------------------------------------------------------------------------------------------- | ---------------------- | ------------------------------------------------------------------------ |
| anyone                       | Anyone can read/write the values. Recommended for reading public information but not writing | Everywhere             | Cannot be used with write and list definitions on user owned definitions |
| definition_owner_only        | Only the user/group who defined the variable can read/write their own value                  | Userspace/Safe context | None                                                                     |
| definition_owner_only_unsafe | Only the user/group who defined the variable can read/write their own value                  | Everywhere             | None                                                                     |
| variable_owner               | Only the user who owns the variable value can read/write their own value                     | Userspace/Safe context | Cannot be used for list                                                  |
| variable_owner_unsafe        | Only the user who owns the variable value can read/write their own value                     | Everywhere             | Cannot be used for list                                                  |

##### User

| Type                                  | Description | Locations              | Limitations             |
| ------------------------------------- | ----------- | ---------------------- | ----------------------- |
| definition_owner_only_contacts        | ?           | Userspace/Safe context | Cannot be used for list |
| definition_owner_only_contacts_unsafe | ?           | Everywhere             | Cannot be used for list |
| variable_owner_only_contacts          | ?           | Userspace/Safe context | Cannot be used for list |
| variable_owner_only_contacts          | ?           | Everywhere             | Cannot be used for list |

##### Group

| Type                    | Description                                               | Locations              | Limitations |
| ----------------------- | --------------------------------------------------------- | ---------------------- | ----------- |
| definition_owner        | Only the group who defined the variable can read/write it | Userspace/Safe context | None        |
| definitioN_owner_unsafe | Only the group who defined the variable can read/write it | Everywhere             | None        |
