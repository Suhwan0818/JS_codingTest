# JadenCase 문자열 만들기  
[프로그래머스 JadenCase 문자열 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12951)  

생각한 내용은 `charAt`을 활용해 첫번째 글자만 `toUpperCase`로 대문자로 만들고 그대로 출력하는 것입니다.  
```js
function solution(s) {
    return s.split(" ").map(value => {
        return value.charAt(0).toUpperCase() + value.slice(1)
    }).join(" ")
} 
```  
그런데 틀렸다고 출력이 됩니다. 알고보니 첫 번째를 대문자로 만들고 그 뒤에 문자는 모두 소문자로 만들어야 합니다. 간단하게 `slice`값에 `toLowerCase`를 추가함으로써 해결했습니다.  

```js
function solution(s) {
    return s.split(" ").map(value => {
        return value.charAt(0).toUpperCase() + value.slice(1).toLowerCase()
    }).join(" ")
} 
```  
결과는 다음과 같습니다.  
![JadenCase_문자열_만들기](/img/JadenCase%20%EB%AC%B8%EC%9E%90%EC%97%B4%20%EB%A7%8C%EB%93%A4%EA%B8%B0%20%EA%B2%B0%EA%B3%BC.PNG)  
나름 잘 만들었다 생각합니다. 가장 효율적으로 해결한 다른 사람 풀이 역시 같은 방식으로 짰다는 것을 알 수 있었습니다.  
 