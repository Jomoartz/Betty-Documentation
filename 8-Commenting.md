# 8 Commenting

Comments are good, but there is also a danger of over-commenting.  
**NEVER** try to explain HOW your code works in a comment: it's much better to write the code so that the _working_ is obvious, and it's a waste of time to explain badly written code.

Generally, you want your comments to tell WHAT your code does, not HOW.
Also, try to avoid putting comments inside a function body: if the function is so complex that you need to separately comment parts of it, you should probably go back to chapter 6 for a while.  
You can make small comments to note or warn about something particularly clever (or ugly), but try to avoid excess.  
Instead, put the comments at the head of the function, telling people what it does, and possibly WHY it does it.

When commenting your functions, please use the kernel-doc format.
See the Chapter about documentation and the script `kernel-doc` from Betty for details.

Linux style for comments is the C89 style.

```C
/* Use this */
```

Don't use C99-style comments

```C
// Don't use this
```

The preferred style for long (multi-line) comments is:

```C
	/*
	 * This is the preferred style for multi-line
	 * comments in the Linux kernel source code.
	 * Please use it consistently.
	 *
	 * Description:  A column of asterisks on the left side,
	 * with beginning and ending almost-blank lines.
	 */
```

It's also important to comment data, whether they are basic types or derived types.  
To this end, use just one data declaration per line (no commas for multiple data declarations).  
This leaves you room for a small comment on each item, explaining its use.