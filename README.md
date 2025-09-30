---
# 🧪 Experiment 17 :- Linked List in C++

---

## 📚 Theory

A **Linked List** is a linear data structure where elements (called nodes) are stored in memory in a non-contiguous manner. Each node contains:

- **Data**: The value of the node
- **Pointer**: A reference to the next node in the list

## Types of Linked Lists:
- **Singly Linked List**: Each node points to the next node and the last node points to NULL.
- **Doubly Linked List**: Each node has two pointers: one to the next and one to the previous node.
- **Circular Linked List**: The last node points back to the head.

---

## ✅ Q1. Insertion at Head (Using Structure)
🔧 Syntax

struct Node {
    int data;
    Node* next;
};
🧠 Logic
Create a new node.

Assign data to the new node.

Point the new node's next to the current head.

Make the new node the new head.

💻 Code
```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

void insertAtHead(Node*& head, int value) {
    Node* newNode = new Node;
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void printList(Node* head) {
    while (head != nullptr) {
        cout << head->data << " -> ";
        head = head->next;
    }
    cout << "NULL" << endl;
}

int main() {
    Node* head = nullptr;

    insertAtHead(head, 30);
    insertAtHead(head, 20);
    insertAtHead(head, 10);

    cout << "Linked List: ";
    printList(head);

    return 0;
}
```

---

## ✅ Q2. Single Linked List Using Class
🔧 Syntax
class Node {
public:
    int data;
    Node* next;
};
🧠 Logic
Create a Node class with data and pointer.

Instantiate nodes using the class.

Link them manually.

💻 Code
```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* next;
};

int main() {
    Node* head = new Node();
    Node* second = new Node();
    Node* third = new Node();

    head->data = 1;
    head->next = second;

    second->data = 2;
    second->next = third;

    third->data = 3;
    third->next = nullptr;

    Node* temp = head;
    while (temp != nullptr) {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL" << endl;

    return 0;
}
```

---

## ✅ Q3. Adding More Nodes Using Class and Printing the Values
🔧 Syntax
class LinkedList {
private:
    Node* head;
public:
    void insert(int val);
    void display();
};
🧠 Logic
Define a LinkedList class to manage the list.

Create a function to insert new nodes at the end.

Create a function to print all values.

💻 Code
```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* next;
    Node(int val) {
        data = val;
        next = nullptr;
    }
};

class LinkedList {
private:
    Node* head;
public:
    LinkedList() {
        head = nullptr;
    }

    void insert(int val) {
        Node* newNode = new Node(val);
        if (head == nullptr) {
            head = newNode;
        } else {
            Node* temp = head;
            while (temp->next != nullptr)
                temp = temp->next;
            temp->next = newNode;
        }
    }

    void display() {
        Node* temp = head;
        while (temp != nullptr) {
            cout << temp->data << " -> ";
            temp = temp->next;
        }
        cout << "NULL" << endl;
    }
};

int main() {
    LinkedList list;
    list.insert(5);
    list.insert(10);
    list.insert(15);
    list.insert(20);

    cout << "Linked List: ";
    list.display();

    return 0;
}
```

---

# ✅ Conclusion
In this experiment, we learned:
1. How linked lists work internally in memory.
2. How to insert a node at the head of a singly linked list.
3. How to use classes in C++ to implement linked list structures.
4. How to dynamically add more nodes and traverse a list.

By understanding these foundational operations, we can build more advanced data structures and algorithms like stacks, queues, and graph representations using linked lists.

---
