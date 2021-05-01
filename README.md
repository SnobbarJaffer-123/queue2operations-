#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
void enqueue();
void dequeue();
void display();
struct node
{
int data;
struct node* next;
};

struct node* front=0;
struct node* rear=0;
void main()
{
int choice;
while(1)
{
printf("\nenqueue operation\n");
printf("dequeue operation\n");
printf("display operation\n");
printf("enter your choice:");
scanf("%d",& choice);
switch(choice)
{
case 1:
enqueue();
break;
case 2:
dequeue();
break;
case 3:
display();
break;
}
}

getch();
}
void enqueue()
{
int val=0;
struct node *temp;
temp=(struct node*)malloc(sizeof(struct node));

printf("enter the element:");
scanf("%d",&val);
temp->data=val;
temp->next=NULL;

if(rear==NULL)
{
front=temp;
rear=temp;
}
else
{
rear->next=temp;
rear=temp;

}
}
void dequeue()
{
if(front==NULL)
{
printf("queue is empty");
}
else
{
printf("\n\nRemoving the front element %d from queue",front->data);
front=front->next;
}


}
void display()
{
if(rear==NULL)
{
printf("the queue is emptyyy");
}
else
{
printf("\ncurrently the queue is :\n");
struct node*temp=front;
while(temp!=NULL)
{
printf("%d\t",temp->data);
temp=temp->next;
}
}
}
