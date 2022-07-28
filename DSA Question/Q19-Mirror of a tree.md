# Mirror of a tree [Link](https://www.geeksforgeeks.org/create-a-mirror-tree-from-the-given-binary-tree/)

Given a binary tree, the task is to create a new binary tree which is a mirror image of the given binary tree.

## Example 1 :

- Input:
   ```
           5
          / \
         3   6
        / \
       2   4
   ```
- Output:
  - Inorder of original tree: 2 3 4 5 6 
  - Inorder of mirror tree: 6 5 4 3 2

- Explaination : Mirror tree will be:
  ```
        5
       / \
      6   3
         / \
        4   2
  ```

## Example 2 :

- Input :
  ```
        2
       / \
      1   8
     /     \
    12      9
  ```
- Output :
  - Inorder of original tree: 12 1 2 8 9 
  - Inorder of mirror tree: 9 8 2 1 12


## Solution

```C++
      #include <iostream>
      #include <vector>
      using namespace std;

      class Node{                      // creating tree with class Node
          public:
          int data;
          Node* left;
          Node* right;

          Node(int val){               // creating new node in tree 
              data = val;
              left = NULL;
              right = NULL;
          }
      };


      void inorder(Node* node,vector<int> &v){        // inorder traversal of the tree 
          if(node==NULL){
              return;                                 // left root right
          }
          inorder(node->left,v);
          v.push_back(node->data);
          inorder(node->right,v);
      }

      Node* mirrortree(Node* root){             // creating mirror of the tree
          if(root==NULL) return root;

          Node* t = root->left;                 // changing the node right to left and left to right
          root->left = root->right;
          root->right = t;

          if(root->left!=NULL)
          mirrortree(root->left);
          if(root->right!=NULL)
          mirrortree(root->right);

          return root;
      }

      int main() {
        Node *root = new Node(5);            // creating root of the tree
        Node *head = root;

        root->left = new Node(3);               // inseting node
        root->right = new Node(6);        

        root->left->left = new Node(2);
        root->left->right = new Node(4);

      // 	root->right->left = new Node(6);
      // 	root->right->right = new Node(7);

        vector<int> vr;                   // to store the root data of the tree nodes in inorder manner

        inorder(head,vr);

        cout<<"Answer real : "<<endl;              // display real image of the tree in inorder traversal

        for(auto &i:vr){
            cout<<i<<" ";
        }

        vector<int> vi;                   // to store the root data of the tree nodes in inorder manner

        head = mirrortree(head);          // creating mirror of the given tree 

        inorder(head,vi);

        cout<<endl<<"Answer mirror : "<<endl;      // display mirror image of the tree in inorder traversal

        for(auto &i:vi){
            cout<<i<<" ";
        }

        return 0;
      }

```
