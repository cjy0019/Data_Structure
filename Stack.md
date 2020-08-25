# 스택(Stack)

- 데이터를 제한적으로 접근할 수 있는 구조
  - 한쪽 끝에서만 자료를 넣거나 뺄 수 있는 구조
- 가장 나중에 쌓은 데이터를 가장 먼저 빼낼 수 있는 구조
  - 큐 : FIFO 정책
  - 스택 : LIFO 정책



### 대표적인 스택의 활용

- 컴퓨터 내부의 프로세스 구조의 함수 동작 방식

#### 주요 기능

- push() : 데이터를 스택에 넣기
- pop() : 데이터를 스택에서 꺼내기
- top() : 스택의 가장 윗 데이터를 반환한다. 만약 스택이 비었다면 이 연산은 정의불가 상태임
- empty() : 스택이 비었다면 1을 반환하고 그렇지 않다면 0을 반환한다.

<img src="http://www.fun-coding.org/00_Images/stack.png" style="zoom: 67%;" />

## 스택 구조와 프로세스 스택

- 스택 구조는 프로세스 실행 구조의 가장 기본
- 함수 호출시 프로세스 실행 구조를 스택과 비교해서 이해 필요



## 스택의 장단점

- 장점
  - 구조가 단순해서 구현이 쉽다
  - 데이터 저장/읽기 속도가 빠르다
- 단점
  - 데이터 최대 갯수를 미리 정해야 한다.
  - 저장 공간의 낭비가 발생할 수 있다.

## 배열로 Stack 구현

```javascript
function stack_pop() {
  var data = data_list.pop();
  console.log(data);
}

var data_list = new Array();

data_list.push(1);
data_list.push(2);
data_list.push(3);
data_list.push(4);
data_list.push(5);

console.log(data_list);  // [1,2,3,4,5]
stack_pop(); // 5
stack_pop(); // 4
stack_pop(); // 3
stack_pop(); // 2
```



