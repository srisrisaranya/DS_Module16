# Ex20 AVL Tree - Deletion
## DATE:
## AIM:
To write a C function to delete an element from an AVL Tree.
## Algorithm
```
1. Search for the node to delete starting from the root. 
2. Delete the node using standard BST rules. 
3. Update the height of the affected nodes. 
4. Calculate the balance factor of each updated node. 
5. Perform rotations if the node is unbalanced. 
6. Continue until the tree is balanced again.
```  
## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: SARANYA S
RegisterNumber:  212223110044
*/
```
```
node * Delete(node *T,int x)
{
    //type your code here
    node *p;
    if(T==NULL)
    {
        return NULL;
    }
    else if(x>T->data)
    {
        T->right=Delete(T->right,x);
        if(BF(T)==2)
        {
            if(BF(T->left)>=0)
            T=LL(T);
        else
        T=LR(T);
        }
    }
    else if(x<T->data)
    {
        T->left=Delete(T->left,x);
        if(BF(T)==-2)
        {
            if(BF(T->right)<=0)
            T=RR(T);
            
        else
        T=RL(T);
        }
    }
    else
    {
        if(T->right!=NULL)
        {
            p=T->right;
            while(p->left!=NULL)
            p=T->left;
            T->data=p->data;
            T->right=Delete(T->right,p->data);
            if(BF(T)==2)
            {
                if(BF(T->left)>=0)
                T=LL(T);
                else
                T=LR(T);
            }
        }
        else
        return(T->left);
    }
    T->ht=height(T);
    return T;
}
```
## Output:
![image](https://github.com/user-attachments/assets/96154907-1e8a-40cb-bfe2-a36e5020b6e6)

## Result:
Thus, the C program to delete an element from an AVL Tree is implemented successfully.
