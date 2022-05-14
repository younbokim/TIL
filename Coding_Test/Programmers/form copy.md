```JavaScript
function solution(s) {
    var answer = '';

    if (s.length % 2 === 0) {
        answer = s.slice(s.length / 2 - 1, s.length / 2 + 1);        
    } else {
        answer = s.slice(s.length / 2 - 0.5);        
    }
    return answer;
}
```


```JavaScript
function solution(a, b) {
    var answer = 0;
    var max = Math.max(a,b);
    var min = Math.min(a,b);

    for(var i=min; i<=max; i++) {
        answer+=i;
    }
    return answer;
}
```

``````JavaScript
function solution(num) {   
    var answer = '';
    if (num % 2 == 0) {
        return 'Even'
    } else
        return 'Odd'
    return answer;
}
```
