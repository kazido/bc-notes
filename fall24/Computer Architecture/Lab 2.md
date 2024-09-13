Name: Bryson Ellalasingham
Prof: Dr. tenBroek
Date: September 11, 2024
Lab: 2

**Q1**: To initialize `p` so that it points to `x`, we could do the following code:
```c
int p* = &x;
```

**Q2:** If `p` was passed instead of `*p` to `printf` it would print the address that was stored in `p` rather than the dereferenced value.

**Q3:** If we dereferenced a pointer that had the value of `NULL`, I would imagine it would either throw an error or it would print null in the form of an address.

**Q4:**  
```c
int *v = &t;
printf("%d\n", *v);
```
If `int *v = &t;` was ran it would attempt to set the `int` value of `v` to the address of `t`, which wouldn't work since the types do not match.

**Q5:** 
`sizeof(int)`is `4`.
`sizeof(3.14)` is `8`.

**Q6:** Show bytes prints out the next bytes after the passed pointer.
Print all printed many, many 0's until I got a "segmentation fault" message in the terminal. 
Printing all as characters game me strange tokens which I usually see when I try to show the bytes in VSCode.