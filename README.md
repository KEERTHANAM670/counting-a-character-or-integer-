# counting-a-character-or-integer-
from itertools import product
n,m=map(int,input().split())
l=list(product("RG",repeat=m))
t=""
z=""
r=[]
for j in range(0,len(l)):
        f=0
        z=""
        t=""
        t=l[j][0]
        for k in range(1,len(l[j])):
            if(l[j][k]==t):
                f=1
                break
            else:
                t=l[j][k]
        if(f!=1):
            for k in range(0,len(l[j])):
                z=z+l[j][k]
            r.append(z)
res=0
for z in range(0,n):
    m=input()
    result=[]
    for i in range(0,len(r)):
        count=0
        for j in range(0,len(r[i])):
            for k in range(0,len(m)):
                if(j==k):
                    if(r[i][j]!=m[k]):
                        if(m[k]=='G'):
                            count=count+3
                        else:
                            count=count+5
        result.append(count)
    res=res+min(result)
print(res)
