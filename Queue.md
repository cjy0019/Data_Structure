# 큐(Queue)

## 큐(Queue) 란?

- 데이터를 집어넣을 수 있는 선형(linear) 자료형이다
- 줄을 서는 행위와 유사하다
- 가장 **먼저 넣은 데이터를 가장 먼저 꺼낼 수 있는 구조** 줄여서 FIFO(First In First Out)라고 부른다
- 데이터를 집어넣는 enqueue, 데이터를 추출하는 dequeue 등의 작업을 할 수 있다.

![](https://www.fun-coding.org/00_Images/queue.png)

출처:http://www.stoimen.com/blog/2012/06/05/computer-algorithms-stack-and-queue-data-structure



### 배열로 큐를 다루는 enqueue, dequeue 기능 구현해보기

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



## 

## 자바스크립트 배열 선언

```javascript
var arrNumber = new Array(); // 배열 선언
var arrNumber = new Array('a','b','c');
var arrNumber = [1,2,3,4];
```

### 자바스크립트 배열의 함수들

1. push는 배열의 끝에 원하는 값을 추가한다

```javascript
var example = new Array('a','b','c');
example.push('d');

console.log(example);
// a,b,c,d
```

2. pop은 배열의 마지막 주소에 있는 값을 제거해준다

```javascript
var example = new Array('a','b','c');
example.pop();

console.log(example);
// a,b
```

3. shift는 배열의 첫번째 주소에 있는 값을 제거하여 반환해준다.

```javascript
var example = new Array('a','b','c');
example.shift();

console.log(example);
// b,c
```

4. length는 배열의 길이를 반환해준다

```javascript
var example = new Array('a','b','c');

console.log(example.length);
// 3
```

5. concat은 두개의 배열을 합쳐주는 기능을 한다

```javascript
var example = new Array('a','b','c');
var example2 = new Array('d','e','f');

example = example.concat(example2);
console.log(example);
// a,b,c,d,e,f
```

6. join을 사용하면 배열값 사이에 원하는 문자를 삽입할 수 있다.

```javascript
var example = new Array('a', 'b', 'c');
example = example.join('/');

console.log(example);
// a/b/c
```

7. reverse를 사용하면 배열을 역순으로 재배치 할 수 있다.

```javascript
var example = new Array('a','b','c');
example.reverse();

console.log(example)
// c,b,a
```

8. sort를 사용하면 배열을 정렬할 수 있다.

```javascript
var example = new Array(1,4,2,3,5);
example.sort();

document.write(example);
// 1,2,3,4,5
```

9. slice는 배열의 일부분을 반환하는 함수이다.

   - slice(start,end)

   - start

     음수를 지정한 경우 : 배열의 끝에서부터 길이를 나타낸다. slice(-2)를 하면 배열의 마지막 2개 요소를 추출한다
     배열의 길이와 같거나 큰 수를 지정한 경우 : 빈 배열을 반환한다

   - end

     음수를 지정한 경우: 배열의 끝에서부터 길이를 나타낸다. slice(2, -1)를 하면 세번째부터 끝에서 두번째 요소까지 추출

```javascript
var example = [1,2,3,4];
var example2 = example.slice(0,-1);

console.log(example);

example2 = example.slie(-2);
cosole.log(example2);

// 1,2,3,4
// 3,4
```

10 . splice는 배열값을 추가하거나 제거하여 반환해주는 함수이다.

```javascript
var example = ['a','b','c','d'];
var example2 = example.splice(1,2);

console.log(example);
console.log(example2);

// a,d
// b,c
```

