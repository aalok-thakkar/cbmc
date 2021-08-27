# History Variables

### Syntax

```c
__CPROVER_old(*identifier*)
```

Refers to the value of a given object in the pre-state of a function within the
_ensures_ clause.

**Important.** This function may be used only within the context of `__CPROVER_ensures`.

### Parameters

`__CPROVER_old` takes a single argument, which is the identifier
corresponding to a parameter of the function. For now, only scalars,
pointers, and struct members are supported.

### Semantics

To illustrate the behavior of `__CPROVER_old`, take a look at the example
below.  If the function returns a failure code, the value of `*out` should not
have been modified.

```c
int sum(const uint32_t a, const uint32_t b, uint32_t* out)
/* Postconditions */
__CPROVER_ensures((__CPROVER_return_value == FAILURE) ==> (*out == __CPROVER_old(*out)))
/* Writable Set */
__CPROVER_assigns(*out)
{
  /* ... */
}
```

### Syntax

```c
__CPROVER_loop_entry(*identifier*)
```

Refers to the value of a given object at the start of the loop.

**Important.** This construct may be used only within the context of 
`__CPROVER_loop_invariant`.

### Parameters

`__CPROVER_loop_invariant` takes a single argument, which is an expression. For now, 
only scalars, pointers, and struct members are supported.

### Semantics

To illustrate the behavior of `__CPROVER_loop_entry`, take a look at the example
below.  

```c
[TODO]
```

### Syntax

```c
__CPROVER_loop_old(*identifier*)
```

Refers to the value of a given object in the previous iteration of the loop.

**Important.** This construct may be used only within the context of 
`__CPROVER_loop_invariant`.

### Parameters

`__CPROVER_loop_invariant` takes a single argument, which is an expression. For now, 
only scalars, pointers, and struct members are supported.

### Semantics

To illustrate the behavior of `__CPROVER_loop_old`, take a look at the example
below.  

```c
[TODO]
```
