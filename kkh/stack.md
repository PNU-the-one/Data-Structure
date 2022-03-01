# stack

LIFO(Last In First Out) 의 구조로, 가장 마지막에 삽입된 요소가 가장 먼저 제거된다.

### 연산

- **top :** 스택의 가장 꼭대기 즉, 마지막에 삽입한 요소의 위치를 가리킨다.
- **push(item) :** 요소를 스택에 삽입할 때 사용한다. top을 1 증가시킨다. 삽입 시 max size 보다 많은 요소가 스택에 존재해선 안된다.
- **pop() :** 요소를 스택에서 제거할 때 사용한다. top을 1 감소시킨다. 스택에 아무것도 존재하지 않을 때, 즉 top index가 -1일 때는 요소를 제거할 수 없다.

<aside>
❓ stack은 위 push pop 연산을 통해서만 스택 내부에 값을 삽입하고 제거할 수 있다.

</aside>

### 구현

```jsx
const stack = () => {
  const arr = Array.from({ length: 100000 }).map((v) => null);
  let top = -1;
  const push = (param) => {
    arr[++top] = param;
  };
  const pop = () => {
    if (isEmpty()) return -1;
    const result = arr[top];
    arr[top--] = null;
    return result;
  };
  const size = () => {
    return top + 1;
  };
  const isEmpty = () => {
    return top === -1 ? 1 : 0;
  };
  const getTop = () => {
    return arr[top] || -1;
  };
  return { push, pop, size, isEmpty, getTop };
};
```

- max length를 100,000으로 설정함.
- 초기 top index를 -1로 설정.
- arr는 push, pop 함수로만 접근 가능하도록 클로저를 통해 구현함.
