# 덱(Deque)

Double-Ended Queue의 줄임말로, front와 rear 모두 삽입과 삭제가 가능한 큐



- **addFront(x)** : 요소 x를 덱의 맨 앞에 추가
- **addRear(x)** : 요소 x를 덱의 맨 뒤에 추가
- **deleteFront()** : 큐의 맨 앞의 요소를 삭제하고 반환
- **deleteRear()** : 큐의 맨 뒤의 요소를 삭제하고 반환
- **getFront()** : 큐의 맨 앞의 요소를 삭제하지 않고 반환
- **getRear()** : 큐의 맨 뒤의 요소를 삭제하지 않고 반환
- isEmpty() : 큐가 비어있으면 true 아니면 false 반환
- isFull() : 큐가 가득 차 있으면 true 아니면 false 반환
- size() : 큐 내의 모든 요소 개수를 반환
- display() : 큐 내의 모든 요소 출력