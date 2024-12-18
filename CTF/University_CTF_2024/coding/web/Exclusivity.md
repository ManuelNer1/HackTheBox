![alt text](image.png)

```
n = input()
l = n.split()
nl = []

for i in l:
    if i in nl:
        print()
    else:
        nl.append(i)

re = " ".join(nl)
print(re)
```