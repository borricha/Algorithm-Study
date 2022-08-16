https://school.programmers.co.kr/learn/courses/30/lessons/42748
---

```python
def solution(array, commands):
    answer = []
    for c in commands:
        arr = array[c[0]-1:c[1]]
        arr.sort()
        answer.append(arr[c[2]-1])
        print(arr)
    return answer
```
