include<iostream>
#define MAXSIZE 3

using namespace std;
int rear=-1,front=-1,queue[MAXSIZE],ele;

void insert()
{
if(front==(rear+1) % MAXSIZE)
{
cout<<"Queue is full";
}
else
{
rear=(rear+1) % MAXSIZE;
if(front==-1)
{
front=0;
}
cout<<"Enter an element\n";
cin>>ele;
queue[rear]=ele;
cout<<"Element"<<ele<<"is inserted at "<<rear;
}
}
void del()
{
if(front==-1 || (front>rear))
{
cout<<"Queue is empty";
}
else
{
ele=queue[front];
front=(front+1);
cout<<"Element"<<ele<<"is deleted";
if((rear==(MAXSIZE-1) && front == 0 )|| (front>rear))
{
front=-1;
rear=-1;

}
}
}
void display(){
int i ;
if(front==-1 || rear==-1)
{
cout<<"\n queue contents are :\t";
for(i=front;i<=rear;i++)
{
cout<<queue[i]<<"\t";

}
}
}
int main
{
int n;
while(n!=4)
{
cout<<"\n Enter what you want do \n"<<"1.insert"  <<"t"<<"2.delete" <<"\t"  <<"3.display"  <<"\t"<<"4.exit" <<"\t"<<"\n";
cin>>n;
switch(n)
{
case1:
insert();
break;
case2:
del();
break;
case 3 :
display();
break;
}
}
if(n==4)
{
cout<<"exit"<<"\n";
}
return 0;
}
