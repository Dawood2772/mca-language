---
layout: page
title: "Control statements"
category: doc
date: 2015-09-30 17:43:20
---

Control statements are used to modify 'code flow'. They allow code to conditionally be run, run multiple times, etc.

MCA currently has 3 control statements:

 - **`if/else`** - conditionally executes code
 - **`while/dowhile`** - executes code continuously while a condition is true
 - **`switch`** - executes different code based on different values

These are covered in more detail below.

## `if/else`

The `if` statement allows code to be conditionally executed. 

### Structure

The `if` statement uses the following structure:

```
if (condition) {
	code
}
```

Where `condition` is an expression, and `code` is the code to be run if the condition evaluates to a truthy value (for more info on this, see the [Types reference page]({{site.baseurl}}/doc/scopes.html)).

Optionally, an `else` block can be added to the end. This block uses the following structure:

```
if (condition) {
	code
} else {
	else code
}
```

In this case, if `condition` evaluates to a falsey value, `else code` will be run _instead_ of `code`. This is functionally the same as the following:

```
if (condition) {
	code
}
if (!condition) {
	else code
}
```

_Best Practice: Always use `else` where possible instead of adding another `if` block with an inverted condition. The `else` block will execute faster, and also looks neater and is easier to understand._

## `while/dowhile`

The `while` statement allows code to be executed multiple times.

### Structure

The `while` statement uses the following structure:

```
while (condition) {
	code
}
```

Where `condition` is an expression, and `code` is the code to be run repedetively. `code` will be run _while_ `condition` evaluates to a truthy value (for more info on this, see the [Types reference page]({{site.baseurl}}/doc/scopes.html)).

The `while` statement always runs the condition _before_ the body. This means that the body might never be executed if the condition evaluates to `false` the first time.

Another, similar statement is the `dowhile` statement. Unlike `while`, `dowhile` executes the condition _after_ the body. This means that the body will always be executed at least once. The `dowhile` statement has the following structure:

```
do {
	code
} while (condition);
```

## `switch`

_To do_