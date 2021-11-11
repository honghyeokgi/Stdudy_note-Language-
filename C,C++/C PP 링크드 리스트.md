##### C PP 링크드 리스트

--------------------------------------------------------------------------------

C언어 함수 포인터

``` c++
#include <iostream>

using namespace std;

struct node
{
	int data;
	node* nextnode;

};

class LinkedList {
private:
	node* head;
	node* tail;

public:
	LinkedList() {
		head = NULL;
		tail = NULL;
	}

	void addFrontNode(int n);

	void addLastNode(int n);

	void addNode(node* prevNode, int n);

	void deleteNode(node* prevNode);

	node* gethead()
	{
		return head;
	}
	void display(node* head);
};

void LinkedList::addFrontNode(int n)
{
	node* temp = new node;
	temp->data = n;

	if (head == NULL)
	{
		head = temp;
		tail = temp;
	}
	else
	{
		temp->nextnode = head;
		head = temp;
	}

}

void LinkedList::addLastNode(int n)
{
	node* temp = new node;
	temp->data = n;

	if (head == NULL)
	{
		head = temp;
		tail = temp;
	}
	else
	{
		tail->nextnode = temp;
		tail = temp;
	}

}

void LinkedList::addNode(node* prevNode, int n)
{
	node* temp = new node;
	temp->data = n;

	temp->nextnode = prevNode->nextnode;
	prevNode->nextnode = temp;

}

void LinkedList::deleteNode(node* prevNode)
{
	node* temp = prevNode->nextnode;
	prevNode->nextnode = temp->nextnode;

	delete temp;

}

void LinkedList::display(node* head)
{
	if (head == NULL)
	{
		cout << "노드가 비어있습니다.\n";
	}
	else
	{
		cout << head->data ;
		display(head->nextnode);
	}
}

int main()
{
	LinkedList a;

	a.addFrontNode(1);	
	a.addFrontNode(2);
	a.addNode(a.gethead(), 3);
	a.addLastNode(4);
	a.display(a.gethead());
    
	return 0;
}
```

