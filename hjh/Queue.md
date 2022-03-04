# 큐(Queue)

양쪽이 뚫려있는 리스트에서 한쪽으로는 데이터를 삽입하고 한쪽으로는 데이터를 삭제하는 자료구조

- 선입선출(FIFO: First In, First Out)

![image-20220304173536299](C:\Users\gkgpa\AppData\Roaming\Typora\typora-user-images\image-20220304173536299.png)

데이터는 Rear로 들어와서 Front로 나간다.

## 큐의 동작

### Enqueue

Rear 위치에 데이터를 삽입한다.



### Dequeue

Front 위치의 데이터를 삭제한다.



### peek

Front 위치의 데이터를 꺼내지 않고 확인하는 작업을 peek라 한다.

![image-20220304174020590](C:\Users\gkgpa\AppData\Roaming\Typora\typora-user-images\image-20220304174020590.png)

### isEmpty

현재 큐가 비어있는지 확인하는 작업이다.

![image-20220304174149688](C:\Users\gkgpa\AppData\Roaming\Typora\typora-user-images\image-20220304174149688.png)



## 코드

### Python List

```
class Queue():
    def __init__(self):
        self.queue = []
        
    def enqueue(self, data):
        self.queue.append(data)
        
    def dequeue(self):
        dequeue_object = None
        if self.isEmpty():
            print("Queue is Empty")
        else:
            dequeue_object = self.queue[0]
            self.queue = self.queue[1:]
            
        return dequeue_object
            
    def peek(self):
        peek_object = None
        if self.isEmpty():
            print("Queue is Empty")
        else:
            peek_object = self.queue[0]
            
        return peek_object
            
    def isEmpty(self):
        is_empty = False
        if len(self.queue) == 0:
            is_empty = True
        return is_empty
```





### Python Single Linked List

```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedListQueue():
    def __init__(self):
        self.front = None
        self.rear = None
        
    def enqueue(self, data):
        new_node = Node(data)
        
        if self.front is None:
            self.front = new_node
            self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = self.rear.next
        
    def dequeue(self):
        dequeue_object = None
        if self.isEmpty():
            print("Queue is Empty")
        else:
            dequeue_object = self.front.data
            self.front = self.front.next
            
        if self.front is None:
            self.rear = None
        return dequeue_object
    
    def peek(self):
        front_object = None
        if self.isEmpty():
            print("Queue is Empty")
        else:
            front_object = self.front.data            
        return front_object
    
    def isEmpty(self):
        is_empty = False
        if self.front is None:
            is_empty = True
        return is_empty
```

