# Advanced Algorithms on Trees

BST Basic Operations

The basic operations that can be performed on a binary search tree data structure, are the following −

-   Insert − Inserts an element in a tree/create a tree.
    
-   Search − Searches an element in a tree.
    
-   Preorder Traversal − Traverses a tree in a pre-order manner.
    
-   Inorder Traversal − Traverses a tree in an in-order manner.
    
-   Postorder Traversal − Traverses a tree in a post-order manner.
    

We shall learn creating (inserting into) a tree structure and searching a data item in a tree in this chapter. We shall learn about tree traversing methods in the coming chapter.

Insert Operation

The very first insertion creates the tree. Afterwards, whenever an element is to be inserted, first locate its proper location. Start searching from the root node, then if the data is less than the key value, search for the empty location in the left subtree and insert the data. Otherwise, search for the empty location in the right subtree and insert the data.

Algorithm :

  ```

If root is NULL

then create root node

return

If root exists then

compare the data with node.data

while until insertion position is located

If data is greater than node.data

goto right subtree

else

goto left subtree

endwhile

insert data

end If

  ```

Implementation

The implementation of insert function should look like this −

Implementation :
```cpp
void insert(int data)
{

    struct node *tempNode = (struct node *)malloc(sizeof(struct node));

    struct node *current;

    struct node *parent;

    tempNode->data = data;

    tempNode->leftChild = NULL;

    tempNode->rightChild = NULL;

    //if tree is empty, create root node

    if (root == NULL)
    {

        root = tempNode;
    }
    else
    {

        current = root;

        parent = NULL;

        while (1)
        {

            parent = current;

            //go to left of the tree

            if (data < parent->data)
            {

                current = current->leftChild;

                //insert to the left

                if (current == NULL)
                {

                    parent->leftChild = tempNode;

                    return;
                }
            }

            //go to right of the tree

            else
            {

                current = current->rightChild;

                //insert to the right

                if (current == NULL)
                {

                    parent->rightChild = tempNode;

                    return;
                }
            }
        }
    }
}
```

    Code :
```

    void
    insert(int data)
{

    struct node *tempNode = (struct node *)malloc(sizeof(struct node));

    struct node *current;

    struct node *parent;

    tempNode->data = data;

    tempNode->leftChild = NULL;

    tempNode->rightChild = NULL;

    //if tree is empty

    if (root == NULL)
    {

        root = tempNode;
    }
    else
    {

        current = root;

        parent = NULL;

        while (1)
        {

            parent = current;

            //go to left of the tree

            if (data < parent->data)
            {

                current = current->leftChild;

                //insert to the left

                if (current == NULL)
                {

                    parent->leftChild = tempNode;

                    return;
                }

            } //go to right of the tree

            else
            {

                current = current->rightChild;

                //insert to the right

                if (current == NULL)
                {

                    parent->rightChild = tempNode;

                    return;
                }
            }
        }
    }
}

```
Search Operation

Whenever an element is to be searched, start searching from the root node, then if the data is less than the key value, search for the element in the left subtree. Otherwise, search for the element in the right subtree. Follow the same algorithm for each node.

Algorithm :
```
If root.data is equal to search.data

return root

else

while data not found

If data is greater than node.data

goto right subtree

else

goto left subtree

If data found

return node

endwhile

return data not found

end if
```  
Implementation :
```cpp
struct node* search(int data)
{

    struct node *current = root;

    printf("Visiting elements: ");

    while (current->data != data)
    {

        if (current != NULL)

            printf("%d ", current->data);

        //go to left tree

        if (current->data > data)
        {

            current = current->leftChild;
        }

        //else go to right tree

        else
        {

            current = current->rightChild;
        }

        //not found

        if (current == NULL)
        {

            return NULL;
        }

        return current;
    }
}
``` ##Code :
```cpp

    struct node *
    search(int data)
{

    struct node *current = root;

    printf("Visiting elements: ");

    while (current->data != data)
    {

        if (current != NULL)
        {

            printf("%d ", current->data);

            //go to left tree

            if (current->data > data)
            {

                current = current->leftChild;

            } //else go to right tree

            else
            {

                current = current->rightChild;
            }

            //not found

            if (current == NULL)
            {

                return NULL;
            }
        }
    }

    return current;
}
```
## 



Tree Traversals :

Traversal is a process to visit all the nodes of a tree and may print their values too. Because, all nodes are connected via edges (links) we always start from the root (head) node. That is, we cannot randomly access a node in a tree. There are three ways which we use to traverse a tree −

-   In-order Traversal
    
-   Pre-order Traversal
    
-   Post-order Traversal
    

Generally, we traverse a tree to search or locate a given item or key in the tree or to print all the values it contains.

## In-order Traversal

In this traversal method, the left subtree is visited first, then the root and later the right sub-tree. We should always remember that every node may represent a subtree itself.

If a binary tree is traversed in-order, the output will produce sorted key values in an ascending order.

![In Order Traversal](https://lh3.googleusercontent.com/lftw-C8CRDrIEsVZNoWBdyNthAFH5L4-B4nfPk4kzv6Y9ej0sNRY0zO6uBCkAYcqKoHzOx-mSeL_XXZJ_h7sMWP27HuExneB2DG66IGKzcWVgSTpzb7amvG99gQxas-9UC4LEASt)

We start from A, and following in-order traversal, we move to its left subtree B. B is also traversed in-order. The process goes on until all the nodes are visited. The output of inorder traversal of this tree will be −

D → B → E → A → F → C → G

### Algorithm

Until all nodes are traversed −

Step 1 − Recursively traverse left subtree.

Step 2 − Visit root node.

Step 3 − Recursively traverse right subtree.

## Pre-order Traversal

In this traversal method, the root node is visited first, then the left subtree and finally the right subtree.

![Pre Order Traversal](https://lh6.googleusercontent.com/jOIfE7dQJKx8uHysm09oIxCBF6swQtqtvnaLI5z4qHfQuMepUPDkZp3sur81rnaIKfjRvWJmPX2wwY2eq3Fm9SWlrHsny--paoa_w3Go-au29T_SXJjy_2VE7vOoxw2nGioZrcyD)

We start from A, and following pre-order traversal, we first visit A itself and then move to its left subtree B. B is also traversed pre-order. The process goes on until all the nodes are visited. The output of pre-order traversal of this tree will be −

A → B → D → E → C → F → G

### Algorithm

Until all nodes are traversed −

Step 1 − Visit root node.

Step 2 − Recursively traverse left subtree.

Step 3 − Recursively traverse right subtree.
  
## Post-order Traversal

In this traversal method, the root node is visited last, hence the name. First we traverse the left subtree, then the right subtree and finally the root node.

![Post Order Traversal](https://lh3.googleusercontent.com/lb0NiSKy4PkNzublWOShE4Pc0pVkts8AfCujGTQFfiPHyYQe0dxJRRG1jOjWgd13myqD_vEfnhgUA-l7AAIAOwOT4otarhSROu8uZ88WW1NlJ_WOGXBFtDDWFn4w4Xd_6kKbWHbk)

We start from A, and following Post-order traversal, we first visit the left subtree B. B is also traversed post-order. The process goes on until all the nodes are visited. The output of post-order traversal of this tree will be −

D → E → B → F → G → C → A

### Algorithm

Until all nodes are traversed −

Step 1 − Recursively traverse left subtree.

Step 2 − Recursively traverse right subtree.

Step 3 − Visit root node.
    
Code :
```cpp

#include <stdio.h>

#include <stdlib.h>









struct node {
    int data;

    struct node *leftChild;

    struct node *rightChild;





};









struct node *root = NULL;









void insert(int data)  {
    struct node *tempNode = (struct node *)malloc(sizeof(struct node));

    struct node *current;

    struct node *parent;

    tempNode->data = data;

    tempNode->leftChild = NULL;

    tempNode->rightChild = NULL;

    //if tree is empty

    if (root == NULL)
    {

        root = tempNode;
    }
    else
    {

        current = root;

        parent = NULL;

        while (1)
        {

            parent = current;

            //go to left of the tree

            if (data < parent->data)
            {

                current = current->leftChild;

                //insert to the left

                if (current == NULL)
                {

                    parent->leftChild = tempNode;

                    return;
                }

            } //go to right of the tree

            else
            {

                current = current->rightChild;

                //insert to the right

                if (current == NULL)
                {

                    parent->rightChild = tempNode;

                    return;
                }
            }
        }
    }





}









struct node* search(int data)  {
    struct node *current = root;

    printf("Visiting elements: ");

    while (current->data != data)
    {

        if (current != NULL)

            printf("%d ", current->data);

        //go to left tree

        if (current->data > data)
        {

            current = current->leftChild;
        }

        //else go to right tree

        else
        {

            current = current->rightChild;
        }

        //not found

        if (current == NULL)
        {

            return NULL;
        }
    }

    return current;





}









void  pre_order_traversal(struct node* root)  {
    if (root != NULL)
    {

        printf("%d ", root->data);

        pre_order_traversal(root->leftChild);

        pre_order_traversal(root->rightChild);
    }





}









void  inorder_traversal(struct node* root)  {
    if (root != NULL)
    {

        inorder_traversal(root->leftChild);

        printf("%d ", root->data);

        inorder_traversal(root->rightChild);
    }





}









void  post_order_traversal(struct node* root)  {
    if (root != NULL)
    {

        post_order_traversal(root->leftChild);

        post_order_traversal(root->rightChild);

        printf("%d ", root->data);
    }





}









int main()  {
    int i;

    int array[7] = {27, 14, 35, 10, 19, 31, 42};

    for (i = 0; i < 7; i++)

        insert(array[i]);

    i = 31;

    struct node *temp = search(i);

    if (temp != NULL)
    {

        printf("[%d] Element found.", temp->data);

        printf("\n");
    }
    else
    {

        printf("[ x ] Element not found (%d).\n", i);
    }

    i = 15;

    temp = search(i);

    if (temp != NULL)
    {

        printf("[%d] Element found.", temp->data);

        printf("\n");
    }
    else
    {

        printf("[ x ] Element not found (%d).\n", i);
    }

    printf("\nPreorder traversal: ");

    pre_order_traversal(root);

    printf("\nInorder traversal: ");

    inorder_traversal(root);

    printf("\nPost order traversal: ");

    post_order_traversal(root);

    return 0;

}


```
```
## Output :

Visiting elements: 27 35 [31] Element found.

Visiting elements: 27 14 19 [ x ] Element not found (15).

Preorder traversal: 27 14 10 19 35 31 42

Inorder traversal: 10 14 19 27 31 35 42

Post order traversal: 10 19 14 31 42 35 27
  ```
What if the input to binary search tree comes in a sorted (ascending or descending) manner? It will then look like this −

![Unbalanced BST](https://lh4.googleusercontent.com/g26flRzrCp6e_LfM067AxFVorlAHjurMmsKI8yz7ulBGfelJ7BKKJM1DRRzquowbEiTh8V7ZQhq5qWR9PQWISw_Hc4ugQRUkkYSluCjit0SKh6hdQ7EIg-_j2e3zAc7QwS_VW0d-)

It is observed that BST's worst-case performance is closest to linear search algorithms, that is Ο(n). In real-time data, we cannot predict data pattern and their frequencies. So, a need arises to balance out the existing BST.

Named after their inventor Adelson, Velski & Landis, AVL trees are height balancing binary search tree. AVL tree checks the height of the left and the right sub-trees and assures that the difference is not more than 1. This difference is called the Balance Factor.

Here we see that the first tree is balanced and the next two trees are not balanced −

![Unbalanced AVL Trees](https://lh6.googleusercontent.com/PEFdBfC1r4xV21Uvab8tjc-EijSUka_rd6DaL7tN1OFSAozYNni2DQtcdWepG0uHO0N3quqZzZLrfMwrtHOeQX9Fr5weaQkanOZqKxiPrDtOUhyKrqcSHENoPCM2aL8vAtWlOIsN)

In the second tree, the left subtree of C has height 2 and the right subtree has height 0, so the difference is 2. In the third tree, the right subtree of A has height 2 and the left is missing, so it is 0, and the difference is 2 again. AVL tree permits difference (balance factor) to be only 1.

BalanceFactor = height(left-sutree) − height(right-sutree)

If the difference in the height of left and right sub-trees is more than 1, the tree is balanced using some rotation techniques.

## AVL Rotations

To balance itself, an AVL tree may perform the following four kinds of rotations −

-   Left rotation
    
-   Right rotation
    
-   Left-Right rotation
    
-   Right-Left rotation
    

The first two rotations are single rotations and the next two rotations are double rotations. To have an unbalanced tree, we at least need a tree of height 2. With this simple tree, let's understand them one by one.

### Left Rotation

If a tree becomes unbalanced, when a node is inserted into the right subtree of the right subtree, then we perform a single left rotation −

![Left Rotation](https://lh6.googleusercontent.com/pFmzZ-s7C2RLfXqxrUg0gBAF1lubo4I2AuRTq3AVU2zQuvAhCUa4TNzOySffQFWfszJWAMfMbzH8eZyXk2Q_Phxhj4Fb-DYW58xTWjvQc569iA0WbdAFsqt_DJLeCzcjL-qLpzud)

In our example, node A has become unbalanced as a node is inserted in the right subtree of A's right subtree. We perform the left rotation by making A the left-subtree of B.

## Right Rotation

AVL tree may become unbalanced, if a node is inserted in the left subtree of the left subtree. The tree then needs a right rotation.

![Right Rotation](https://lh5.googleusercontent.com/GZReo5QMXnJvNTDVdCVGGJcPpnv66OkY91DKoq09KKU5w7sHYyyjMOWYZqOD7xa_uUsDaFysUN-1F5I9iU_VCiyiSrM6kII7GBDKWNGKUyLYlCquLHGgBdbeILJtYLJD-TL1gRXC)

As depicted, the unbalanced node becomes the right child of its left child by performing a right rotation.

### Left-Right Rotation

Double rotations are slightly complex version of already explained versions of rotations. To understand them better, we should take note of each action performed while rotation. Let's first check how to perform Left-Right rotation. A left-right rotation is a combination of left rotation followed by right rotation.

State

Action

![Right Rotation](https://lh3.googleusercontent.com/lMyi-mCkJl0id9-WizaJYgiFyw3uQj7FjyR23Y77JDkeaf-W60vBDvDrDSFqrSfUxPz-3KjIxVMiCCRDBcd5oq2koui3hYigIKCBdJFRFwLFyB__qFsCXqWBXU5H6puZA_Nc3nUW)

A node has been inserted into the right subtree of the left subtree. This makes C an unbalanced node. These scenarios cause AVL tree to perform left-right rotation.

![Left Rotation](https://lh6.googleusercontent.com/HTY7cq0QaSi69Wz1T58pT80Q-5TFyD0ggobTfqBA4bieMP89V2sbyFzbK-O4tcLiNG5_SNQzNp1UhzinAZNyP3y8oM9nQ2xKI9mlrzV2Wad9N61sQLpZm0Gzcia0eQdwEM9Jeg1w)

We first perform the left rotation on the left subtree of C. This makes A, the left subtree of B.

![Left Rotation](https://lh4.googleusercontent.com/5JzKEb3yIuLeqz6WH-lBw4nIWSJCqeIMAO9ExbGACZudlf39wvOJuesoiS6E721JpjIQwUeH7a2oAIne7-EQlPblyngU9kcw8eKKlX7mlGDN4usX9Tl8EB068PjbFFzjZ52N4ep5)

Node C is still unbalanced, however now, it is because of the left-subtree of the left-subtree.

![Right Rotation](https://lh4.googleusercontent.com/THvaQSM44qO3KuVotGIwIs9REy4VdoS-BLLHg_wbv4VLC7cgZiNDr_r1ZVSOHVOanJsyOrZow3ZAk6f_dDdps3pmMTm47EAHm3fPcd8Fi93BFJXdp4Qs1SFS3SYyyCupbo_s-oYh)

We shall now right-rotate the tree, making B the new root node of this subtree. C now becomes the right subtree of its own left subtree.

![Balanced Avl Tree](https://lh6.googleusercontent.com/BvsHYMdCCVJmpnbD3nYQtjBJNfNabHPZIAo3eKmjvUubKW3YZ0FtNnBxU9npU48HjDQ25htuheo2uAkU32h0Qi99QDn2cIMsYkhX_U6HXOQNX8gIfX3ag9uuLaxxxomT-FiwmK9x)

The tree is now balanced.

### Right-Left Rotation

The second type of double rotation is Right-Left Rotation. It is a combination of right rotation followed by left rotation.

State

Action

![Left Subtree of Right Subtree](https://lh6.googleusercontent.com/olRyc2z03IFVzPbnxr9xvcEnuWj9N1Zj1qSpmSFO67ytZxeMucO9pvCoFDN1N7KZ0ht_66vDha5E12Ntp7nrxYwazJDH7WTihkW22EMhXzcyl2tlvwNoZEjDkYGIaJERNmkzARHO)

A node has been inserted into the left subtree of the right subtree. This makes A, an unbalanced node with balance factor 2.

![Subtree Right Rotation](https://lh3.googleusercontent.com/H2thEtowFbB75birkApGc2pZX3AytdBQHZR9lbdsugUgHiH2Dy4KYB_n8PbIl_wKQkpqrZoDYHXIcdc2Gqjjainggms6F_oqhrFdiRR062A04RsLGoLZBER1O5TbffH2NOqiqbpy)

First, we perform the right rotation along C node, making C the right subtree of its own left subtree B. Now, B becomes the right subtree of A.

![Right Unbalanced Tree](https://lh3.googleusercontent.com/LJ64Atn_6YJJ4_0-XYvZ3dCQ9bQOX0yAD_qrV_ZIdUmYXPP4cJzxuWiivqSADktGJVbEWHndVXuLk0PZDsIgsuAgK3j4blhWAsGkktF9KlX-HD7bB7ZVWrbNwZQRnRSE5Ey_WZvI)

Node A is still unbalanced because of the right subtree of its right subtree and requires a left rotation.

![Left Rotation](https://lh5.googleusercontent.com/971HNqACnZ--6Ch2GMfPgkzXmxLoOJTJrrvUynCtdbxCpP_zy16w4OBKCaivh5wav968dywSh6KuHgqK1YadiPo7Ewdw19DZER2NprrVYVk8x9wiushwsnPz64JPW-R5GMmdZLdP)

A left rotation is performed by making B the new root node of the subtree. A becomes the left subtree of its right subtree B.

![Balanced AVL Tree](https://lh6.googleusercontent.com/BvsHYMdCCVJmpnbD3nYQtjBJNfNabHPZIAo3eKmjvUubKW3YZ0FtNnBxU9npU48HjDQ25htuheo2uAkU32h0Qi99QDn2cIMsYkhX_U6HXOQNX8gIfX3ag9uuLaxxxomT-FiwmK9x)

<<<<<<< HEAD
The tree is now balanced.
=======
The tree is now balanced.
>>>>>>> 12acb17102afdd9197c4c7738204eccf3da01aa5
