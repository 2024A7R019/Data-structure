//WAP to understand singly linked list
#include<stdio.h>
#include<stdlib.h>
typedef struct node
{
    int data;
    struct node *next;
}Node;
Node* Head = NULL;
Node *CreateNode(int ele)
{
    Node* NewNode = (Node*)malloc(sizeof(Node));
    NewNode -> data = ele;
    NewNode -> next = NULL;
    return NewNode;
}
void insertNodeInBeg(int ele)
{
    Node* NewNode = CreateNode(ele);
    NewNode -> next = Head;
    Head = NewNode;
    printf("Node Inserted !!!\n");
}
void insertNodeAtEnd(int ele)
{
    Node* NewNode = CreateNode(ele);
    if (Head == NULL)
    {
        Head = NewNode;
    }
    else
    {
        Node* temp = Head;
        while (temp -> next != NULL)
        {
            temp = temp -> next;
        }
        temp -> next = NewNode;
    }
    printf("Node Inserted !!!\n");
}
void insertNodeAtAnyPosition(int ele, int position)
{
    if (Head == NULL)
    {
        printf("List is empty !!!\n");
    }
    else if (position == 1)
    {
        insertNodeInBeg(ele);
    }
    else
    {
        int i = 1;
        Node* temp = Head;
        while (i < (position-1) && temp -> next != NULL)
        {
            temp = temp -> next;
            i++;
        }
        if (temp -> next != NULL && i>1)
        {
            Node* NewNode = CreateNode(ele);
            NewNode -> next = temp -> next;
            temp -> next = NewNode;
            printf("Node Inserted !!!\n");
        }
        else
        {
            printf("Invalid Position !!!\n");
        }
    }
}
void deleteNodeFromBeg()
{
    if (Head == NULL)
    {
        printf("List is empty !!!\n");
    }
    else
    {
        Node *temp = Head;
        Head = Head -> next;
        free(temp);
        printf("Node deleted !!!\n");
    }
}
void deleteNodeFromEnd()
{
    if (Head == NULL)
    {
        printf("List is empty !!!\n");
    }
    else
    {
        Node *temporary;
        if (Head -> next == NULL)
        {
            temporary = Head;
            Head = NULL;
        }
        else
        {
        Node *temp = Head;
        while (temp -> next -> next != NULL)
        {
            temp = temp -> next;
        }
        temporary = temp -> next;
        temp -> next = NULL;
        }
        free(temporary);
        printf("Node deleted !!!\n");
    }
}
void deleteNodeFromAnyPosition(int position)
{
    if (Head == NULL)
    {
        printf("List is empty !!!\n");
    }
    else if (position == 1)
    {
        deleteNodeFromBeg();
    }
    else
    {
        int i = 1;
        Node* temp = Head;
        while (i < (position-1) && temp -> next != NULL)
        {
            temp = temp -> next;
            i++;
        }
        if (temp -> next != NULL && position>0)
        {
            Node *temporary = temp ->next;
            temp -> next = temp -> next -> next;
            free(temporary);
            printf("Node Deleted !!!\n");
        }
        else
        {
            printf("Invalid Position !!!\n");
        }
    }
}
void search(int target)
{
    if (Head == NULL)
    {
        printf("List is empty !!!\n");
    }
    else
    {
        Node *temp = Head;
        while (temp != NULL)
        {
            if (temp -> data == target)
            {
                printf("Found !!!\n");
                return;
            }
            temp = temp -> next;
        }
        printf("Not Found !!!\n");
    }
}
void sort()
{
    if (Head == NULL)
    {
        printf("List is empty !!!\n");
    }
    else
    {
        Node* last = NULL;
        for (Node* i = Head; i -> next != NULL; i = i-> next)
        {
            Node* j;
            for (Node* j = Head; j -> next != last; j = j-> next)
            {
                if (j -> data > j -> next -> data)
                {
                    int temp = j -> data;
                    j -> data = j -> next -> data;
                    j -> next -> data = temp;
                }   
            }
            last = j;
        }
    }
}
void display()
{
    if (Head == NULL)
    {
        printf("List is empty");
    }
    else
    {
        Node* temp = Head;
        while (temp != NULL)
        {
            printf("%d ",temp -> data);
            temp = temp -> next;
        }
    }
}
int main()
{
    while (1)
    {
        printf("------ Singly Linked List ------\n");
        printf("1. Insert Node In Beginning\n");
        printf("2. Insert Node At End\n");
        printf("3. Insert Node At Any Position\n");
        printf("4. Delete Node From Beginning\n");
        printf("5. Delete Node From End\n");
        printf("6. Delete Node From Any Position\n");
        printf("7. Search Element In List\n");
        printf("8. Sort Elments\n");
        printf("9. Display List\n");
        printf("10. Exit\n\n");
        int choice,value,pos;
        printf("Enter choice = ");
        scanf("%d",&choice);
        switch (choice)
        {
        case 1:
            printf("Enter Value = ");
            scanf("%d",&value);
            insertNodeInBeg(value);
            break;
        case 2:
            printf("Enter Value = ");
            scanf("%d",&value);
            insertNodeAtEnd(value);
            break;
        case 3:
            printf("Enter Value = ");
            scanf("%d",&value);
            printf("Enter Position = ");
            scanf("%d",&pos);
            insertNodeAtAnyPosition(value,pos);
            break;
        case 4:
            deleteNodeFromBeg();
            break;
        case 5:
            deleteNodeFromEnd();
            break;
        case 6:
            printf("Enter Position = ");
            scanf("%d",&pos);
            deleteNodeFromAnyPosition(pos);
            break;
        case 7:
            printf("Enter Target = ");
            scanf("%d",&value);
            search(value);
            break;
        case 8:
            sort();
            break;         
        case 9:
            display();
            break;
        case 10:
            exit(0);
            break;
        default:
            printf("Invalid choice !!!\n");
            break;
        }
        printf("\n\n");
		system("pause");
    }
    return 0;
}
