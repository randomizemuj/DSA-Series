# Linked List

A linked list is a sequence of data structures, which are connected together via links.

Linked List is a sequence of links which contains items. Each link contains a connection to another link. Linked list is the second most-used data structure after array. Following are the important terms to understand the concept of Linked List.

-   **Link**  − Each link of a linked list can store a data called an element.
    
-   **Next**  − Each link of a linked list contains a link to the next link called Next.
    
-   **LinkedList**  − A Linked List contains the connection link to the first link called First.
    

## Linked List Representation

Linked list can be visualized as a chain of nodes, where every node points to the next node.

![Linked List](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list.jpg)

As per the above illustration, following are the important points to be considered.

-   Linked List contains a link element called first.
    
-   Each link carries a data field(s) and a link field called next.
    
-   Each link is linked with its next link using its next link.
    
-   Last link carries a link as null to mark the end of the list.
    

## Types of Linked List

Following are the various types of linked list.

-   **Simple Linked List**  − Item navigation is forward only.
    
-   **Doubly Linked List**  − Items can be navigated forward and backward.
    
-   **Circular Linked List**  − Last item contains link of the first element as next and the first element has a link to the last element as previous.
    

## Basic Operations

Following are the basic operations supported by a list.

-   **Insertion**  − Adds an element at the beginning of the list.
    
-   **Deletion**  − Deletes an element at the beginning of the list.
    
-   **Display**  − Displays the complete list.
    
-   **Search**  − Searches an element using the given key.
    
-   **Delete**  − Deletes an element using the given key.
    

## Insertion Operation

Adding a new node in linked list is a more than one step activity. We shall learn this with diagrams here. First, create a node using the same structure and find the location where it has to be inserted.

![Linked List Insertion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_insertion_0.jpg)

Imagine that we are inserting a node  **B**  (NewNode), between  **A**  (LeftNode) and  **C**  (RightNode). Then point B.next to C −

NewNode.next −> RightNode;

It should look like this −

![Linked List Insertion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_insertion_1.jpg)

Now, the next node at the left should point to the new node.

LeftNode.next −> NewNode;

![Linked List Insertion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_insertion_2.jpg)

This will put the new node in the middle of the two. The new list should look like this −

![Linked List Insertion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_insertion_3.jpg)

Similar steps should be taken if the node is being inserted at the beginning of the list. While inserting it at the end, the second last node of the list should point to the new node and the new node will point to NULL.

## Deletion Operation

Deletion is also a more than one step process. We shall learn with pictorial representation. First, locate the target node to be removed, by using searching algorithms.

![Linked List Deletion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_0.jpg)

The left (previous) node of the target node now should point to the next node of the target node −

LeftNode.next −> TargetNode.next;

![Linked List Deletion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_1.jpg)

This will remove the link that was pointing to the target node. Now, using the following code, we will remove what the target node is pointing at.

TargetNode.next −> NULL;

![Linked List Deletion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_2.jpg)

We need to use the deleted node. We can keep that in memory otherwise we can simply deallocate memory and wipe off the target node completely.

![Linked List Deletion](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_deletion_3.jpg)

## Reverse Operation

This operation is a thorough one. We need to make the last node to be pointed by the head node and reverse the whole linked list.

![Linked List Reverse Operation](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_0.jpg)

First, we traverse to the end of the list. It should be pointing to NULL. Now, we shall make it point to its previous node −

![Linked List Reverse Operation](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_1.jpg)

We have to make sure that the last node is not the last node. So we'll have some temp node, which looks like the head node pointing to the last node. Now, we shall make all left side nodes point to their previous nodes one by one.

![Linked List Reverse Operation](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_2.jpg)

Except the node (first node) pointed by the head node, all nodes should point to their predecessor, making them their new successor. The first node will point to NULL.

![Linked List Reverse Operation](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_3.jpg)

We'll make the head node point to the new first node by using the temp node.

![Linked List Reverse Operation](https://www.tutorialspoint.com/data_structures_algorithms/images/linked_list_reverse_4.jpg)

The linked list is now reversed.

## Linked List implementation

```c++
#include  <stdio.h>

#include  <string.h>

#include  <stdlib.h>

#include  <stdbool.h>

  

struct  node {

int  data;

int  key;

struct  node  *next;

};

  

struct  node  *head = NULL;

struct  node  *current = NULL;

  

//display the list

void  printList() {

struct  node  *ptr = head;

printf("\n[ ");

//start from the beginning

while(ptr != NULL) {

printf("(%d,%d) ",ptr->key,ptr->data);

ptr = ptr->next;

}

printf(" ]");

}

  

//insert link at the first location

void  insertFirst(int  key, int  data) {

//create a link

struct  node  *link = (struct  node*) malloc(sizeof(struct node));

link->key = key;

link->data = data;

//point it to old first node

link->next = head;

//point first to new first node

head = link;

}

  

//delete first item

struct  node*  deleteFirst() {

  

//save reference to first link

struct  node  *tempLink = head;

//mark next to first link as first

head = head->next;

//return the deleted link

return  tempLink;

}

  

//is list empty

bool  isEmpty() {

return  head == NULL;

}

  

int  length() {

int  length = 0;

struct  node  *current;

for(current = head; current != NULL; current = current->next) {

length++;

}

return  length;

}

  

//find a link with given key

struct  node*  find(int  key) {

  

//start from the first link

struct  node*  current = head;

  

//if list is empty

if(head == NULL) {

return  NULL;

}

  

//navigate through list

while(current->key != key) {

//if it is last node

if(current->next == NULL) {

return  NULL;

} else {

//go to next link

current = current->next;

}

}

//if data found, return the current Link

return  current;

}

  

//delete a link with given key

struct  node*  delete(int  key) {

  

//start from the first link

struct  node*  current = head;

struct  node*  previous = NULL;

//if list is empty

if(head == NULL) {

return  NULL;

}

  

//navigate through list

while(current->key != key) {

  

//if it is last node

if(current->next == NULL) {

return  NULL;

} else {

//store reference to current link

previous = current;

//move to next link

current = current->next;

}

}

  

//found a match, update the link

if(current == head) {

//change first to point to next link

head = head->next;

} else {

//bypass the current link

previous->next = current->next;

}

return  current;

}

  

void  sort() {

  

int  i, j, k, tempKey, tempData;

struct  node  *current;

struct  node  *next;

int  size = length();

k = size ;

for ( i = 0 ; i < size - 1 ; i++, k-- ) {

current = head;

next = head->next;

for ( j = 1 ; j < k ; j++ ) {

  

if ( current->data > next->data ) {

tempData = current->data;

current->data = next->data;

next->data = tempData;

  

tempKey = current->key;

current->key = next->key;

next->key = tempKey;

}

current = current->next;

next = next->next;

}

}

}

  

void  reverse(struct  node**  head_ref) {

struct  node*  prev = NULL;

struct  node*  current = *head_ref;

struct  node*  next;

while (current != NULL) {

next = current->next;

current->next = prev;

prev = current;

current = next;

}

*head_ref = prev;

}

  

void  main() {

insertFirst(1,10);

insertFirst(2,20);

insertFirst(3,30);

insertFirst(4,1);

insertFirst(5,40);

insertFirst(6,56);

  

printf("Original List: ");

//print list

printList();

  

while(!isEmpty()) {

struct  node  *temp = deleteFirst();

printf("\nDeleted value:");

printf("(%d,%d) ",temp->key,temp->data);

}

printf("\nList after deleting all items: ");

printList();

insertFirst(1,10);

insertFirst(2,20);

insertFirst(3,30);

insertFirst(4,1);

insertFirst(5,40);

insertFirst(6,56);

printf("\nRestored List: ");

printList();

printf("\n");

  

struct  node  *foundLink = find(4);

if(foundLink != NULL) {

printf("Element found: ");

printf("(%d,%d) ",foundLink->key,foundLink->data);

printf("\n");

} else {

printf("Element not found.");

}

  

delete(4);

printf("List after deleting an item: ");

printList();

printf("\n");

foundLink = find(4);

if(foundLink != NULL) {

printf("Element found: ");

printf("(%d,%d) ",foundLink->key,foundLink->data);

printf("\n");

} else {

printf("Element not found.");

}

printf("\n");

sort();

printf("List after sorting the data: ");

printList();

reverse(&head);

printf("\nList after reversing the data: ");

printList();

}
```

*Output*

```
Original List: 
[ (6,56) (5,40) (4,1) (3,30) (2,20) (1,10) ]
Deleted value:(6,56) 
Deleted value:(5,40) 
Deleted value:(4,1) 
Deleted value:(3,30) 
Deleted value:(2,20) 
Deleted value:(1,10) 
List after deleting all items: 
[ ]
Restored List: 
[ (6,56) (5,40) (4,1) (3,30) (2,20) (1,10) ]
Element found: (4,1) 
List after deleting an item: 
[ (6,56) (5,40) (3,30) (2,20) (1,10) ]
Element not found.
List after sorting the data: 
[ (1,10) (2,20) (3,30) (5,40) (6,56) ]
List after reversing the data: 
[ (6,56) (5,40) (3,30) (2,20) (1,10) ]
```