---
title: "Common components"
---

# Common components

This page describes how to use very common components.

${toc}

## ValueUserOverride

The component `ValueUserOverride<T>` can be found in `Transform`->`Driver` and is used to override a value locally for a user.

It takes a few options in to work:

- `Target` - Which value you with to locally override
- `PersistentOverrides` - When checked, the overrides will persist after saving the map or object in question
- `Default` - Sets the default value for someone that doesn't have an override
- `CreateOverrideOnWrite` - Makes it so when someone changes the value, an override will be created automatically for them

Overrides may also be created manually by refencing a userid (`U-<snowflake ID>`) and a value.
