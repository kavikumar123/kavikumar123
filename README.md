program 9

#include <iostream.h>
const int SIZE = 5;
class Queue {
 int arr[SIZE];
 int front, rear;
public:
 Queue() {
 front = rear = -1;
 }
 void enqueue(int value) {
 if (rear == SIZE - 1) {
 cout << "Queue Overflow!" << endl;
 } else {
 arr[++rear] = value;
 if (front == -1) front = 0;
 cout << value << " added to the queue." << endl;
 }
 }
 void dequeue() {
 if (front == -1) {
 cout << "Queue Underflow!" << endl;
 } else {
 cout << arr[front] << " removed from the queue." << endl;
 if (front == rear) front = rear = -1;
 else front++;
}
 }
 void display() {
 if (front == -1) {
 cout << "Queue is empty." << endl;
 } else {
 cout << "Queue elements: ";
 for (int i = front; i <= rear; i++) {
 cout << arr[i] << " ";
 }
 cout << endl;
 }
 }
};
int main() {
 Queue q;
 q.enqueue(1);
 q.enqueue(2);
 q.enqueue(3);
 q.display();
 q.dequeue();
 q.display();
 return 0;
}
