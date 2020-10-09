# 링크드 리스트(Linked List)

`연결 리스트`라고도 한다.

**배열 vs 링크드 리스트**

- 배열은 순차적을 연결된 공간에 데이터를 나열하는 데이터 구조
- 링크드 리스트는 떨어진 곳에 존재하는 데이터를 **화살표로 연결**해서 관리하는 데이터 구조



## 링크드 리스트 기본 구조와 용어

- **노드(Node)** : 데이터의 저장 단위(데이터 값, 포인터로) 구성된다.
- **포인터(pointer)** : 각 노드 안에서, 다음이나 이전의 노드와의 연결 정보를 가지고 있는 공간이다.

![node.png](https://github.com/cjy0019/Data_Structure/blob/master/images/node.png?raw=true)

#### 링크드 리스트의 특징

1. 연속되는 항목들이 포인터로 연결된다.

<img src="https://www.fun-coding.org/00_Images/linkedlist.png" />

(출처: wikipedia, https://en.wikipedia.org/wiki/Linked_list)

2. 마지막 항목은 Null을 가리킨다.
3. 프로그램이 수행되는 동안 크기가 커지거나 작아질 수 있다.
4. (시스템 메모리가 허용하는 한) 필요한 만큼 길어질 수 있다.
5. 메모리 공간을 낭비하지 않는다.(대신 포인터를 위한 추가의 메모리를 필요로 한다.)



## 링크드 리스트의 장단점

- 장점
  - 미리 데이터 공간을 할당하지 않아도 됨.
    - 배열은 미리 데이터 공간을 할당 해야 함
- 단점
  - 연결을 위한 별도 데이터 공간이 필요하므로 저장 공간 효율이 높지 않음
  - 연결 정보를 찾는 시간이 필요하므로 접근 속도가 느리다
  - 중간 데이터 삭제시, 앞뒤 데이터의 연결을 재구성해야 하는 부가적인 작업이 필요하다.



## 링크드 리스트 기능

- append(데이터) : 리스트 맨 끝에 데이터를 추가한다.
- removeAt(위치) : 해당 위치에 있는 데이터를 삭제한다.
- IndexOf(데이터) : 해당 데이터의 인덱스를 반환한다.
- remove(데이터) : 데이터를 삭제한다.
- insert(위치, 데이터) : 해당 위치에 데이터를 삽입한다.
- isEmpty() : 데이터가 하나도 없다면 true, 그 외엔 false를 반환한다.
- size() : 데이터 개수를 반환한다.



## 간단한 예시

```javascript
function Node(data){
    this.data = data;
    this.next = null;
}
```



## 링크드 리스트 구현해보기

```javascript
function LinkedList(){
    var _length = 0;
    var _head = null;
}
```

- `_length`는 링크드 리스트에 담긴 데이터의 개수이다.
- `_head`는 연결이 시작되는 지점을 참조한다.