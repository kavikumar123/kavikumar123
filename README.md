program 7:

#include <iostream.h>
class Node {
public:
 int data;
 Node* next;
};
class LinkedList {
public:
 Node* head;
 LinkedList() {
 head = NULL;
 }
 void insert(int data) {
 Node* newNode = new Node();
 newNode->data = data;
 newNode->next = head;
 head = newNode;
 }
 void deleteNode(int data) {
 if (head == NULL) return;
 if (head->data == data) {
 Node* temp = head;
 head = head->next;
 delete temp;
 return;
 }
 Node* current = head;
 while (current->next != NULL) {
 if (current->next->data == data) {
Node* temp = current->next;
 current->next = current->next->next;
 delete temp;
 return;
 }
 current = current->next;
 }
 }
 void printList() {
 Node* current = head;
 while (current != NULL) {
 cout << current->data << " ";
 current = current->next;
 }
 cout << endl;
 }
};
int main() {
 LinkedList list;
 list.insert(10);
 list.insert(20);
 list.insert(30);
 cout << "Linked List: ";
 list.printList();
 list.deleteNode(20);
 cout << "Linked List after deletion: ";
 list.printList();
 return 0;
}
