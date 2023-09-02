# N개의 최소 공배수

[프로그래머스 N개의 최소 공배수](https://school.programmers.co.kr/learn/courses/30/lessons/12953)

최소 공배수를 구하는 공식을 사용하고자 했습니다.

예를 들어 예시로 나온 `[2, 6, 8, 14]`의 최소 공배수는 아래와 같이 해결할 수 있습니다.

```
[2,6,8,14] -> (2*6)/2=6 -> [6,8,14] -> (6*8)/2=24 -> [24,14] -> 24*14/2 -> 168
```

고로 정답은 168이라는 사실을 알 수 있습니다. 단순히 `x*y/최대공약수` 라는 공식을 사용한 방법입니다. 바로 적용해보겠습니다.

```js
function solution(arr) {
  return arr.reduce((a, b) => (a * b) / minVal(a, b))
}

function minVal(a, b) {
  if (b === 0) return a
  return minVal(b, a % b)
}
```

공식만 안다면 크게 어려운 문제는 아니었다 생각합니다.
