// ###########################################################################
// implimantation of two stack on a array 
// with single array memori
// 
// #######################################################################
#include <stdio.h>
#define MAX 10
int top1 = -1;
int top2 = MAX;

void push_element_stack1(int arr[])
{
    if (top1 == top2 - 1)
        printf("\n ***********************--overflow----**************************\n");
    else
    {
        top1++;
        printf("enter your element -> ");
        int input;
        scanf("%d", &input);
        arr[top1] = input;
    }
}

void pop_element_stack1(int arr[])
{
    if (top1 == -1)
        printf("\n*********************---underflow-----****************************\n");
    else
        top1--;
}

void push_element_stack2(int arr[])
{
    if (top1 > top2)
        printf("\n********************************---overflow---****************************************\n");
    else
    {
        top2--;
        printf("enter your element -> ");
        int input;
        scanf("%d", &input);
        arr[top2] = input;
    }
}

void pop_element_stack2(int arr[])
{
    if (top2 == MAX)
        printf("\n***************************---underflow---*******************************\n");
    else
        top2++;
}

void display_element(int arr[])
{
    printf("\n your array is -> ");
    for (int i = 0; i <= top1; i++)
        printf("%d ", arr[i]);
    for (int i = top2; i < MAX; i++)
        printf("%d ", arr[i]);
    printf("\n");
}
// void display_arr(int a)
int main()
{
    int arr[MAX];

    printf("------------------------------------------------------------------------------------------------------------------------------------------\n");
    printf("*****************************************************-----welcome----******************************************************\n");
    printf("choice is your for operation for flowing -> \n");
    printf("------------------------------------------------------------------------------------------------------------------------------------\n");

    while (1)
    {
        printf("________________________________________________________________________________________________________________________\n");
        printf("\t 1.) push_element_Stack1\n");
        printf("\t 2.) push_element_Stack2\n");
        printf("\t 3.) pop_element_stack1\n");
        printf("\t 4.) pop_element_stack2\n");
        printf("\t 5.) display_the_element\n");
        printf("\t 6.)end the programe \n");
        int choice;
        printf("\n___________________________________________________________________________________________________________________\n");
        printf(" enter your choice -> ");
        scanf("%d", &choice);
        switch (choice)
        {
        case 1:
            push_element_stack1(arr);
            break;
        case 2:
            push_element_stack2(arr);
            break;
        case 3:
            pop_element_stack1(arr);
            break;
        case 4:
            pop_element_stack2(arr);
            break;
        case 5:
            display_element(arr);
            break;
        case 6:
            return 0;
        default:
            printf(" \n invalid input \n");
            break;
        }
    }

    return 0;
}
