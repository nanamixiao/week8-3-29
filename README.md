# week8-3-29
## 1 
![{_Y1DI4EF2P@535N2O ~@%P](https://github.com/user-attachments/assets/df3520fa-90c9-4467-a004-ab8e97d4b5b8)

## 2 

log1000 with base 2 = 10

## 3 
current = root
while current.right != null:
        current = current.rightNode
        return current


## 4 

``` .cpp

#include <iostream>

using namespace std;

//template <typename  T, typename  compare = less <T>>
struct Node{

    int theData;
    Node *nextRNode;
    Node *nextLNode;

    Node(int data = 0) : theData(data), nextRNode(nullptr), nextLNode(nullptr) {}
};



class LinkC{
private:
    Node* root;
public:
    LinkC() : root(nullptr) {}





    void insert(int val) {

        Node* newNode = new Node(val);


        if (root == nullptr) {
            root = newNode;
            return;
        }

        Node* current = root;
        Node* parents = nullptr;



        while (current != nullptr) {
            parents = current;
            if (val < (parents->theData))
                current = parents->nextLNode;
            else
                current = parents->nextRNode;
        }



        if (val < (parents->theData))
            parents->nextLNode = newNode;
        else
            parents->nextRNode = newNode;
    }





};

int main() {
    LinkC tree;
    int arr[] = {1, 5, 9, 2, 4, 10, 6, 3, 8};
    int size = std::size(arr);

    for (int i = 0; i < size; i++) {
        tree.insert(arr[i]);
    }



}


```


