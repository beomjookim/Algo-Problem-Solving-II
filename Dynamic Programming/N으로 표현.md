# 프로그래머스


## 브레인 스토밍

TBA... 코드가 너무 더러운데 더 좋은 풀이가 있을랑가?


## 코드

```python
def solution(N, number):
    if number == N: return 1
    dp_table = [['fuck'], [N]]
    
    for i in range(2, 9):                       # i는 2~8로 제한
        ithTable = []
        for j in range(1, (i+2)//2):
            for k in dp_table[j]:
                for l in dp_table[i-j]:
                    ithTable.append(k+l)
                    ithTable.append(k*l)
                    ithTable.append(k-l)
                    ithTable.append(l-k)
                    if k: ithTable.append(l//k)
                    if l: ithTable.append(k//l)
        ithTable.append(int(str(N)*i))
        if number in ithTable: return i
        dp_table.append(list(set(ithTable)))
    return -1
```
