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

### Permissions

// TODO
