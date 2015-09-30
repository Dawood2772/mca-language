---
layout: page
title: "Variables"
category: doc
date: 2015-09-30 19:08:01
---

Variables allow values to be dynamically stored, changed and outputted. MCA supports dynamically-typed variables, that is, variables do not have a preset required type.

## Usage

Accessing a variable can be done by simply using the variables name. For example, see the following code:

**Code:**

```
message = "Hello, World!";
message_length = .str_len(message);

/say The message "{message}" is {message_length} character(s) long;
```

**Becomes:**

```
/say The message "Hello, World!" is 13 character(s) long
```

## Declaration

Variables are created, or 'declared', the first time they are set. This means that trying to use a variable before it has been set will result in an error being fired. However, variables can be set to `null` if they do not need a value yet.

For example:

**Code:**

```
/say {something};
```

**Becomes:**

```
Error!
```

**Code:**

```
something = null;
/say {something};
```

**Becomes:**

```
/say null
```

## Scope

Variables are only available in the block that they are defined in. As a result, variables defined inside a block cannot be accessed from outside of the block. For more information, see [the Scope reference page]({{site.baseurl}}/docs/scopes.html).