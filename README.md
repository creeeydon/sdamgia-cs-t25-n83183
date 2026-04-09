# sdamgia-cs-t25-n83183
Решение задачи (тип 25) №83183,  ссылка: https://inf-ege.sdamgia.ru/problem?id=83183 на **Python**

## Стандартное решение
```python
def prostoe(n):
    k=2
    while k**2 <= n:
        if n%k==0: return False
        k+=1
    return True
n,m = 1475000,0
while m < 5:
    n-=1
    k=2
    d=set()
    while k**2 <= n:
        if n%k==0: d |= {k,n//k}
        k+=1
    sn = sum(x for x in d if prostoe(x))
    if sn > 0 and sn <= 42000 and sn%6==0:
        print(n)
        m+=1
```

## Решение в одну строку
```python
a = (x for x in reversed(range(1_475_000)) if sum(filter((lambda dl: x % dl == 0),set(range(2, 42001)) - {j for i in range(2, int(42000 ** 0.5) + 1) for j in range(i * i, 42001, i)})) if (42000 > sum(filter((lambda dl: x % dl == 0), set(range(2, 42001)) - {j for i in range(2, int(42000 ** 0.5) + 1) for j in range(i * i, 42001, i)})) > 0 == sum(filter((lambda dl: x % dl == 0), set(range(2, 42001)) - {j for i in range(2, int(42000 ** 0.5) + 1) for j in range(i * i, 42001, i)})) % 6)); print([next(a) for i in (range(5))])
```
