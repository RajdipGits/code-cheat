class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class Queue:
    def __init__(self):
        self.front = None
        self.rear = None

    def enqueue(self, data):
        new = Node(data)

        if self.rear is None:
            self.front = self.rear = new
        else:
            self.rear.next = new
            self.rear = new

        print("Inserted:", data)

    def dequeue(self):
        if self.front is None:
            print("Queue is Empty")
        else:
            print("Deleted:", self.front.data)
            self.front = self.front.next

            if self.front is None:
                self.rear = None

    def isempty(self):
        return self.front is None

    def isfull(self):
        return False

    def display(self):
        if self.front is None:
            print("Queue is Empty")
        else:
            temp = self.front
            while temp:
                print(temp.data, end=" ")
                temp = temp.next
            print()


q = Queue()

q.enqueue(10)
q.enqueue(20)
q.enqueue(30)

q.display()

q.dequeue()

q.display()

print("Is Empty:", q.isempty())
print("Is Full:", q.isfull())
