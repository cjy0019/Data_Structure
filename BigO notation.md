# 빅오 표기법

- 알고리즘을 구현하는 법을 학습하기 전에 알고리즘이 얼마나 효과적인지 분석하는 방법을 이해해야 한다.
- **시간은 실행 시간, 공간은 사용된 메모리라고 볼 수 있다.**



## 빅오 표기법 기초

- 빅오 표기법은 알고리즘의 최악의 경우 복잡도를 측정한다. 빅오 표기법에서 n은 입력의 개수를 나타낸다. 즉, **알고리즘을 구현할 때 빅오 표기법이 해당 알고리즘이 얼마나 효율적인지 나타내기 때문에 빅오 표기법은 중요하다고 할 수 있다.**

<p align="center"><img src="https://miro.medium.com/max/1590/1*yiyfZodqXNwMouC0-B0Wlg.png" width="350px"/></p>



- O(1)은 입력 공간에 대해 변하지 않는다. 따라서 O(1)을 상수 시간이라고 부른다. 
- 배열에 있는 항목을 인덱스를 사용해 접근하는 경우가 O(1) 알고리즘의 예다.
- O(n)은 **선형 시간**이고  최악의 경우에 n번의 연산을 수행해야 한다.



ex) 0부터 `n-1`까지의 숫자를 출력하는 경우

```javascript
function exampleLinear(n) {
  for (var i = 0; i < n; i++) {
    console.log(i);
  }
}
```

**마찬가지로 O(n<sup>2</sup>)은 2차 시간이고 O(n<sup>3</sup>)은 3차 시간이다. 2차 시간과 3차 시간 복잡도는 다음과 같다.**

```javascript
// 2차 시간 복잡도
function exampleQuadratic(n) {
  for (var i = 0; i < n; i++) {
    console.log(i);
    for (var j = i; j < n; j++) {
      console.log(j);
    }
  }
}
```

```javascript
///3차 시간 복잡도
function exampleCubic(n) {
  for (var i = 0; i < n; i++) {
    console.log(i);
    for (var j = i; j < n; j++) {
      console.log(j);
      for (var k = j; k < n; k++) {
        console.log(k);
      }
    }
  }
}
```

**로그 시간 복잡도를 지닌 알고리즘의 예는 2의 2승부터 n승까지의 항목들을 출력하는 경우가 있다.** 로그 시간 복잡도의 효율은 백만 개의 항목처럼 큰 입력이 있는 경우 분명하다. n이 백만이라고 하더라도 log<sub>2</sub>(1,000,000) = 19.9315686 이기 때문이다.

```javascript
// 로그 시간 복잡도
// 2의 2승부터 출력
function exampleLogarithmic(n) {
  for (var i = 2; i <= n; i *= 2) {
    console.log(i);
  }
}
```



## 빅오 표기법 규칙

알고리즘의 시간 복잡도를 `f(n)`이라고 표현할 때, n은 입력의 개수를 나타내고 **f(n)<sub>time</sub>**은 필요한 시간을 나타내고 **f(n)<sub>space</sub>**는 필요한 공간(추가적인 메모리)을 나타낸다.

- **계수 법칙** : 상수 k가 0보다 크다고 할 때(k > 0), f(n)이 O(g(n))이면 kf(n)은 O(g(n))이다. 이는 입력 크기 n과 관련되지 않은 계수를 제거한다. n이 무한에 가까워질 때 다른 계수는 무시해도 되기 때문이다.

- **합의 법칙** : f(n)이 O(h(n))이고 g(n)이 O(p(n))이면 f(n)+g(n)은 O(h(n)+p(n))이다. 합의 법칙은 결과값인 시간 복잡도가 두 개의 다른 시간 복잡도의 합이라면 결과값인 빅오 표기법 역시 두 개의 다른 빅오 표기법의 합이라는 것을 의미한다.
- **곱의 법칙** : f(n)이 O(h(n))이고 g(n)이 O(p(n))이면 f(n)g(n)은 O(h(n)p(n))이다. 두 개의 다른 시간 복잡도를 곱할 때 빅오 또한 곱해진다.
- **전이 법칙** : f(n)이 O(g(n))이고 g(n)이 O(h(n))이면 f(n)은 O(h(n))이다.
- **다항 법칙** : f(n)이 k차 다항식이면 f(n)은 O(n<sup>k</sup>)이다. 직관적으로 다항 법칙은 다항 시간 복잡도가 동일한 다항 차수의 빅오 표기법을 지닌다.



### 계수 법칙 : 상수를 제거하라

- 단순히 입력 크기와 연관되지 않은 상수를 전부 무시한다.
- 빅오에서 입력 크기가 클 때 게수를 무시할 수 있다.

상수 k > 0 인 경우 f(n)이 f(n)이 O(g(n))이면 kf(n)은 O(g(n))이다.

```javascript
function a(n) {
  var count = 0;
  for (var i = 0; i < n; i++) {
    count += 1;
  }
  return count;
}
```

위 예제는 f(n)=n이다. count에 숫자를 n번 더하기 때문이다. 따라서 시간 복잡도는 **O(n)**이다.

```javascript
function a(n) {
  var count = 0;
  for (var i = 0; i < 5 * n; i++) {
    count += 1;
  }
  return count;
}
```

위 예제의 f(n)=5n이다. 0부터 5n까지 실행하기 때문이다. **그러나 두 코드 모두 O(n)의 빅오 표기법을 지닌다.** n이 충분히 클 때 위의 코드가 n번 수행된다고 할 수 있다. 즉 빅오 표기법에서 모든 상수는 무시해도 된다.

```javascript
function a(n) {
  var count = 0;
  for (var i = 0; i < n; i++) {
    count += 1;
  }
  count += 3;
  return count;
}
```

위의 코드는 f(n)=n+1이다. 마지막 연산으로 인해 +1이 추가됐다. 하지만 여전히 O(n)의 빅오 표기법이다.



### 합의 법칙 : 빅오를 더하라

시간 복잡도를 더할 수 있다는 것이다.

f(n)이 O(h(n))이고 g(n)이 O(p(n))이라면 f(n) + g(n)은 O(h(n)+p(n))이다. **합의 법칙을 적용한 다음 계수 법칙을 적용해야 한다는 점에 주의하자**

```javascript
function a(n) {
  var count = 0;
  for (var i = 0; i < n; i++) {
    count += 1;
  }
  for (var i = 0; i < 5 * n; i++) {
    count += 1;
  }
  return count;
}
```

위의 예제는 두 개의 메인 루프를 포함하는데 각 루프의 시간 복잡도는 개별적으로 계산된 다음 더해져야 한다. 네 번째 줄은 f(n)=n에 해당하고 일곱 번째 줄은 f(n)=5n에 해당한다. 결과값은 6n이 되지만 계수 법칙을 적용하여 O(n)=n이다.



### 곱의 법칙 : 빅오를 곱하라

f(n)이 O(h(n))이고 g(n)이 O(p(n))이면 f(n)g(n)은 O(h(n)p(n))이다.

```javascript
function mulO(n) {
  var count = 0;
  for (var i = 0; i < n; i++) {
    count += 1;
    for (var i = 0; i < 5 * n; i++) {
      count += 1;
    }
  }
  return count;
}
```

위의 예에서 f(n)= 5n*n이다. 여섯 번째 줄이 내부 루프에 의해 5n번 실행되고 내부 루프가 외부 루프에 의해 n번 실행되기 때문이다. 따라서 결과는 5<sup>2</sup>번 연산이 일어난다. 결과는 O(n)=n<sup>2</sup>



### 다항 법칙 : 빅오의 K승

f(n)이 k차 다항식이면 f(n)은 O(n<sup>k</sup>)이다.

```javascript
function a(n) {
  var count = 0;
  for (var i = 0; i < n * n; i++) {
    count += 1;
  }
  return count;
}
```

위의 예에서 f(n)=n<sup>2</sup>이다. 네 번째 줄이 n*n회 실행되기 때문이다.