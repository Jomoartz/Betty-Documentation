Linux kernel style for use of spaces depends (mostly) on function-versus-keyword usage.  
Use a space after (most) keywords.  
The notable exceptions are `sizeof`, `typeof`, `alignof`, and `__attribute__`, which look somewhat like functions (and are usually used with parentheses in Linux, although they are not required in the language, as in: `sizeof info` after `struct fileinfo info;` is declared).

So use a space after these keywords:

```C
	if, switch, case, for, do, while
```

but not with `sizeof`, `typeof`, `alignof`, or `__attribute__`.  
**E.g.:**

```C
	s = sizeof(struct file);
```

Do not add spaces around (inside) parenthesized expressions.  
This example is **bad**:

```C
	s = sizeof( struct file );
```

When declaring pointer data or a function that returns a pointer type, the preferred use of `*` is adjacent to the data name or function name and not adjacent to the type name.  
**Examples:**

```C
	char *str;
	unsigned int sample(char *ptr, char **retptr);
	char *match_strdup(substring_t *s);
```

Use one space around (on each side of) most binary and ternary operators, such as any of these:

```C
	=  +  -  <  >  *  /  %  |  &  ^  <=  >=  ==  !=  ?  :
```

but no space after unary operators:

```C
	&  *  +  -  ~  !  sizeof  typeof  alignof  __attribute__  defined
```

no space before the postfix increment & decrement unary operators:

```C
	++  --
```

no space after the prefix increment & decrement unary operators:

```C
	++  --
```

and no space around the `.` and `->` structure member operators.

Do not leave trailing whitespace at the ends of lines.  
Some editors with `smart` indentation will insert whitespace at the beginning of new lines as appropriate, so you can start typing the next line of code right away.
However, some such editors do not remove the whitespace if you end up not putting a line of code there, such as if you leave a blank line.  
As a result, you end up with lines containing trailing whitespace.

Git will warn you about patches that introduce trailing whitespace, and can optionally strip the trailing whitespace for you; however, if applying a series of patches, this may make later patches in the series fail by changing their context lines.