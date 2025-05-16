# EX 57 C function to perfom push,pop and peek functions in Stack using Linked List.( store float data in stack)
## DATE:
## AIM:
To write a C function to perfom push,pop and peek functions in Stack using Linked List.

## Algorithm

## Program:
```
/*
function to perfom push,pop and peek functions in Stack using Linked List.( store float data in stack)

Developed by: Sowjanya A
RegisterNumber:  212222060250
*/
#include <stdio.h>
#include <stdlib.h>

struct Node {
    float data;
    struct Node* next;
};

void push(struct Node** top, float value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
}

float pop(struct Node** top)
{
    if (*top == NULL)
    {
        printf("Stack underflow.\n");
        return -1;
    }
    struct Node* temp = *top;
    float poppedData = temp->data;
    *top = (*top)->next;
    free(temp);
    return poppedData;
}

float peek(struct Node* top)
{
    if (top == NULL)
    {
        printf("Stack is empty.\n");
        return -1;
    }
    return top->data;
}

int main()
{
    struct Node* stack = NULL;

    push(&stack, 10.5);
    push(&stack, 20.7);
    push(&stack, 30.9);
    
    printf("Top element (peek): %.2f\n", peek(stack));

    printf("Popped element: %.2f\n", pop(&stack));
    
    printf("Top element after pop (peek): %.2f\n", peek(stack));

    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/9e928414-3f7b-4399-b8cc-490ff70f07ec)


## Result:
Thus the program was executed and the output was verified successfully.
