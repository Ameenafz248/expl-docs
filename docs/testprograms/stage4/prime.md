---
title: 'Prime or Not'
---

```
decl
    int n,i,j;
enddecl
    read(n);
    j=0;
    if (n <= 1) then
        j = 1;
    else
        i=2;
        while(i<=n/2) do
            if(n%i==0) then
                j=1;
            endif;
            i=i+1;
        endwhile;
    endif;
    if(j==0) then
        write("Prime");
    else 
        write("Not Prime");
    endif;
```
