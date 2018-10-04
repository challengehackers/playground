# vulnerable-c

`vulnerable` is a Linux 32-bit binary that contains the functions
`foo()` and `bar()`.  Having been compiled with no stack protection
and when run on a system without ASLR enabled, this program appears
to have some serious vulnerabilities.

Original C source code is not provided except for this snippet of
the `bar()` routine:

```
void bar() {
        printf("You called bar()\n");
}
```

## Buffer Overflow Exploit

Your objective is to get the `foo()` routine to run by using a buffer
overflow exploit so that the string "You called bar()" is output.

Your answer should be formatted as a single line of text consisting of
pairs of hex characters separated by spaces.  Any pad characters for the
overflow should be a properly encoded lower case 'a'.  You should assume
that the hex pairs would be converted into a string that would then be
redirected to STDIN for the program.

Hint: Use the GNU Debugger on an isolated 32-bit sandbox system without
ASLR enabled when working with this binary.

Note: Each person's answer may differ slightly due to differences in
memory layout at run time, but the challenge is easily solved on any
system once you know how to construct the exploit.  At a later date we
will update this repo with our solution for you to compare with your
own.
