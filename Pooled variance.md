
```R
### Pooled Variance
n1<-10
n2<-10
s1<-3.6
s2<-3.3      
sp <- ((n1-1)*s1^2+(n2-1)*s2^2)/(n1+n2-2)
sqrt(sp)
```