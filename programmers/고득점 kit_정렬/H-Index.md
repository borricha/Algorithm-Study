https://school.programmers.co.kr/learn/courses/30/lessons/42747#
---

전체 n개 중 h 이상인수가 h개 되도록 하는 최대 h 값을 구하는 문제였다. 

n의 값이 그렇게 크지는 않아서 이분탐색을 안해도 상관은 없어보였지만, 일단 이분 탐색으로 먼저 풀어보았다.

```python
def solution(citations):
    answer = 0
    citations.sort()
    max_h = citations[-1]
    min_h = 0
    
    while min_h <= max_h:
        h = (max_h+min_h)//2
        count = 0
        for c in citations:
            if c < h:
                count += 1
            else:
                break
        if len(citations)-count >= h:
            answer = h
            min_h = h + 1
        else:
            max_h = h - 1
        continue
    return answer
```

정렬을 사용한다면

```python
def solution(citations):
    citations = sorted(citations)
    l = len(citations)
    for i in range(l):
        if citations[i] >= l-i:
            return l-i
    return 0
```
이렇게도 풀 수 있을 것 같다. 
