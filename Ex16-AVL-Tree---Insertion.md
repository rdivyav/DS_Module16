# Ex16 AVL Tree - Insertion
## DATE:28.4.25
## AIM:
To write a C function to insert the elements in an AVL Tree.

## Algorithm
1.Normal BST Insertion: Insert the new node into the AVL tree as if it were a standard binary search tree (BST) 
2. Update Heights
3. Calculate Balance Factors
4.Check for Imbalance  
5. Rebalance the Tree   

## Program:
```
/*
Program to insert the elements in an AVL Tree
Developed by:Divya RV 
RegisterNumber:212223100005  
*/
```
```
/*typedef struct node
{
int data;
struct node *left,*right;
int ht;
}node;
node *insert(node *,int);
void preorder(node *);
//void inorder(node *);
int height(node *);
node *rotateright(node *);
node *rotateleft(node *);
node *RR(node *);
node *LL(node *);
node *LR(node *);
node *RL(node *);
int BF(node *);
*/ 
node * insert(node *T,int x)
{
    // type your code here
    if(T==NULL)
    {
        T=(node*)malloc(sizeof(node));
        T->data=x;
        T->left=T->right=NULL;
    }
    else if(x > T->data)
    {
        T->right=insert(T->right,x);
        if(BF(T)==-2)
        {
            if(x > T->right->data)
            T=RR(T);
            else
            T=RL(T);
        }
    }
    else
    {
        T->left=insert(T->left,x);
        if(BF(T)==2)
        {
            if(x < T->left->data)
            T=LL(T);
            else
            T=LR(T);
        }
    }
    T->ht=height(T);
    return T;
}

```
## Output:

![Screenshot 2025-04-29 121129](https://github.com/user-attachments/assets/57bc6b19-0ee1-4374-a073-f43d7317de0b)


## Result:
Thus, the function to insert the elements in an AVL Tree is implemented successfully in C programming language.
