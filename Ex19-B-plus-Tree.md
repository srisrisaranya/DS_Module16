# Ex19 B+ Tree
## DATE:
## AIM:
To write a C function to traverse the elements in a B+ Tree.

## Algorithm
```
1. Start 
2. Iterate through each element in the node's data array. 
3. If the node is not a leaf, recursively call traverse on the current child pointer. 
4. Print the current data element. 
5. After the loop, if the node is not a leaf, traverse the last child pointer. 
6. Return after completing the traversal. 
7. End
``` 
## Program:
```
/*
Program to traverse the elements in a B+ Tree.
Developed by: SARANYA S 
RegisterNumber:  212223110044
*/
```
```
/*struct B_TreeNode
{
    int *data;
    struct B_TreeNode **child_ptr;
    int leaf;
    int n;
};
struct B_TreeNode *root = NULL, *np = NULL, *x = NULL;*/

void traverse(struct B_TreeNode *p)
{
 // type your code here 
 int i;
 for(i=0;i<p->n;i++)
 {
     if(p->leaf==0)
     {
         traverse(p->child_ptr[i]);
     }
     printf("%d ",p->data[i]);
 }
 if(p->leaf==0)
 {
     traverse(p->child_ptr[i]);
 }
}
```
## Output:
![image](https://github.com/user-attachments/assets/82ee6d8d-2c72-4dbf-aed6-a7ca33634c23)

## Result:
Thus, the function to traverse the elements in a B+ Tree is implemented successfully.
