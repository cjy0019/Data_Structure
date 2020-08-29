# 큐(Queue)

## 큐(Queue) 란?

- 데이터를 집어넣을 수 있는 선형(linear) 자료형이다
- 줄을 서는 행위와 유사하다
- 가장 **먼저 넣은 데이터를 가장 먼저 꺼낼 수 있는 구조** 줄여서 FIFO(First In First Out)라고 부른다
- 데이터를 집어넣는 enqueue, 데이터를 추출하는 dequeue 등의 작업을 할 수 있다.



![](https://www.fun-coding.org/00_Images/queue.png)

출처:http://www.stoimen.com/blog/2012/06/05/computer-algorithms-stack-and-queue-data-structure



## 배열로 큐를 다루는 enqueue, dequeue 기능 구현해보기



```javascript
// enqueue
var queue_array = new Array(); // 배열 생성

function enqueue(data) {
  queue_array.push(data);
}  // 배열의 마지막 주소에 하나씩 data를 하나씩 더해줌

for (i = 0; i < 10; i++) {
  enqueue(i);
} // 0부터 9까지 enqueue
console.log(queue_array); //[0,1,2,3,4,5,6,7,8,9]

// dequeue
function dequeue() {
  var data = queue_array[0];
  queue_array.shift();
  console.log(data);
} // data에 queue_array의 0번째 인덱스를 넣고 그 값을 지운후 출력해준다

dequeue(); // 0
dequeue(); // 1
dequeue(); // 2
```

