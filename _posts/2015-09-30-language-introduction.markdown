---
layout: page
title: "Language Introduction"
category: tut
date: 2015-09-30 17:09:59
---

MCA is a macro language. This means that instead of writing code that will run at _runtime_ (like normal programming languages), MCA code will run at _compile time_, and be used to generate the runtime code (i.e [MCIL]({{site.baseurl}}/doc/mcil.html)). MCA also provides a standard library, which includes functions for string operations, mathematical operations, error handling, and some advanced code generation.

The syntax is primarily C-based, however it also borrows from Assembly, and of course the Minecraft command syntax.

## Macros

The majority of operations in MCA are completed with _macros_. Macros are pieces of code that can be repeated in other locations.

Here is an example of a simple macro:

**Code:**

```
// define the macro
#SAY_HELLO /say hello;

// use the macro
SAY_HELLO;
```

**Becomes:**

```
/say hello
```

You can think of macros as the equivalent of _functions_ in standard programming languages. Just like functions, macros can also have **parameters** passed to them. This allows you to pass values into the macro:

**Code:**

```
// define the macro
#GET_ONE_MORE(number) number + 1;

// use the macro
/say {GET_ONE_MORE(1)};
```

**Becomes:**

```
/say 2
```

All of the above examples only allow us to define an "expression" (e.g. addition, or a command) macro. To create more powerful macros, we can use _blocks_.

**Code:**

```
// define the macro
#SAY_AND_ADD(number) {
	/say The number is {number};
	return number + 1;
}

/say And the next number is {SAY_AND_ADD(2)};
```

**Becomes:**

```
/say The number is 2
/say And the next number is 3
```

For more info on macros, see [the Macro reference page]({{site.baseurl}}/doc/macros.html).

## Control statements

Just like regular programming languages, MCA supports _control statements_, like `if`, `while`, and `switch`. Unlike regular languages, however, these are run at _compile time_. For example, this means that it is not possible to check if a player exists in a certain radius with an `if` statement - instead, branching should be used for this.

MCA has 3 control statements:

 - **`if/else`** - conditionally executes code
 - **`while/dowhile`** - executes code continuously while a condition is true
 - **`switch`** - executes different code based on different values

For more info on control statements, see the [Control statements reference page]({{site.baseurl}}/doc/control-statements.html).