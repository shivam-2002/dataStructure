//Tree implementation and traversal

#include<iostream>
using namespace std;
class node
{
	public:
		int data;
		node *left,*right;
};
node *create()
{
	node *p=new node;
	int x;
	cout<<"(-1 for no data)Enter data: ";
	cin>>x;
	if(x==-1)
	{
		return NULL;
	}
	else
	{
		p->data=x;
		cout<<"Enter left child of "<<x<<" : ";
		p->left=create();
		cout<<"Enter right child of "<<x<<" : ";
		p->right=create();
	}
	return p;
}
void inorder(node *t)
{
	if(t!=NULL)
	{
		inorder(t->left);
		cout<<t->data<<" ";
		inorder(t->right);
	}
	
	
}
void preorder(node *t)
{
	if(t!=NULL)
	{
		cout<<t->data<<" ";
		preorder(t->left);
		preorder(t->right);
	}
}
void postorder(node *t)
{
	if(t!=NULL)
	{
		postorder(t->left);
		postorder(t->right);
		cout<<t->data<<" ";
	}
}
int main()
{
	node *root;
	root=create();
	cout<<"\nInorder: ";	
	inorder(root);
	cout<<"\nPreorder: ";
	preorder(root);
	cout<<"\nPostorder: ";
	postorder(root);
}
