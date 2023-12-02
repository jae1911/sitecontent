---
title: "Common components"
---

# Common components

This page describes how to use very common components.

${toc}

## ValueUserOverride

The component `ValueUserOverride<T>` can be found in `Transform`->`Drivers` and is used to override a value locally for a user.

It takes a few options in to work:

- `Target` - Which value you with to locally override
- `PersistentOverrides` - When checked, the overrides will persist after saving the map or object in question
- `Default` - Sets the default value for someone that doesn't have an override
- `CreateOverrideOnWrite` - Makes it so when someone changes the value, an override will be created automatically for them

Overrides may also be created manually by refencing a userid (`U-<snowflake ID>`) and a value.

## ValueCopy

The component `ValueCopy<T>` can be found in `Transform`->`Drivers` and is used to copy a value from a field to another.

It takes in a few options:

- `Source` - The source from which the value is copied
- `Destination` - Where to copy the value
- `WriteBack` - When checked, it means the target can write back its value to the source

Note that it is possible to automatically creating those by grabbing a field, dropping it onto another and selecting the "Drive" option in the context menu that appears.
