# 스택(Stack)
Top이라고 하는 한쪽 끝에서 모든 삽입(push)과 삭제(pop)가 일어나는 순서 리스트

- 후입선출(LIFO: Last-In-First-Out)

<img src="https://blog.kakaocdn.net/dn/bcgR9A/btqSX70PCTe/dMSMQoJcZhDpq4sRRpu3A0/img.png" alt="img" style="zoom: 50%;" />

스택은 완전히 꽉 찼을 경우 Overflow 상태라고 하며 완전히 비어 있으면 Underflow라고 한다.

삽입과 삭제는 모두 Top에서 일어난다.

### 추상 자료형(ADT)

- push - 스택 맨위에 항목을 삽입
- pop - 스택 맨위에 항목 삭제
- peek or top - 스택의 맨 위(top)를 표시
- isEmpty - 스택이 비어있는지 확인
- isFull - 스택이 가득 차 있는지 확인
- getSize - 스택에 있는 요소 수를 반환

## 스택의 동작

### Push

데이터를 넣는 작업을 push라고 한다.

<img src="https://blog.kakaocdn.net/dn/elJvyd/btqTlHglsNW/aEuYC31jnEgzCXgHZqzlBk/img.png" alt="img" style="zoom: 67%;" />

1. 스택이 가득 찼는지 확인
2. 스택이 가득 찼다면, 오류 발생 및 종료
3. 스택이 가득 차지 않았다면, Top 증가
4. Top이 가리키는 곳에 데이터 추가

### Pop

데이터를 제거하는 작업을 pop이라고 한다.

<img src="https://blog.kakaocdn.net/dn/ltr3L/btqTjDFADpN/c5Cxjq1X35Se4gdX2UbEd0/img.png" alt="img"  />

1. 스택이 비어 있는지 확인
2. 스택이 비어 있다면, 오류 발생 및 종료
3. 스택이 비어있지 않다면, Top이 가리키는 데이터 제거
4. Top 감소

## 시간 복잡도

| Operation     | Average | Worst |
| ------------- | ------- | ----- |
| Access        | Θ(n)    | O(n)  |
| Search        | Θ(n)    | O(n)  |
| Insert (push) | Θ(1)    | O(1)  |
| Delete (pop)  | Θ(1)    | O(1)  |

push(), pop(), isEmpty(), peek() 모두 O(1) 시간이 걸리는 이유는 삽입 삭제는 항상 Top에서만 일어나기 때문이다.

## 코드

```
class Stack():
    def __init__(self):
        self.stack = []
        
    def push(self, data):
        self.stack.append(data)
        
    def pop(self):
        pop_object = None
        if self.isEmpty():
            print("Stack is Empty")
        else:
            pop_object = self.stack.pop()
            
        return pop_object
            
    def top(self):
        top_object = None
        if self.isEmpty():
            print("Stack is Empty")
        else:
            top_object = self.stack[-1]
            
        return top_object
            
            
    def isEmpty(self):
        is_empty = False
        if len(self.stack) == 0:
            is_empty = True
        return is_empty
```

