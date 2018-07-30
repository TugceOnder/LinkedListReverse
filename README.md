#include<iostream>
using namespace std;

struct Node
{
    int data;
    struct Node* next;
    Node (int data)
    {
        this->data = data;
        next = NULL;
    }
};
 
struct LinkedList
{
    Node *head;
    LinkedList()
    {
        head = NULL;
    }


void reverseList(LinkedList *L)
{
  Node *current = head;
        Node *prev = NULL, *next = NULL;
 
 
        while (current != NULL)
        {
            // Store next
            next = current->next;
 
            // Reverse current node's pointer
            current->next = prev;
 
            // Move pointers one position ahead.
            prev = current;
            current = next;
        }
        head = prev;
}

 void print()
    {
        struct Node *temp = head;
        while (temp != NULL)
        {
            cout << temp->data << " ";
            temp = temp->next;
        }
    }
 
    void push(int data)
    {
        Node *temp = new Node(data);
        temp->next = head;
        head = temp;
    }
};


int main(){
     LinkedList ll;
     int n;
     cout<< "How many do you give input ";
     cin>>n;

     for (int i =0;i<n; ){
       int a;
       cout<<"Give the input ";
       cin >>a;
       ll.push(a);
       i++;
     }

 
    cout << "linked list\n";
    ll.print();
 
     ll.reverseList(&ll);
 
    cout << "\nReversed Linked list \n";
    ll.print();
    return 0;


}
