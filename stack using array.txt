#include<stdio.h>
#include<stdlib.h>

#define MAX 10

int count=0;

//creating 
struct stack{
    int items[MAX];
    int top;
};

typedef struct stack st;
void createEmptystack(st* s)
{
    s->top=-1;
    
}
//if full
int isfull(st *s){
    if(s->top==MAX-1) 
    return 1;
    else
    return 0;
}
//if overflow
int isEmpty(st *s){
    if(s->top==-1)
     return 1;
    else
     return 0;
} 
    //add element
    void push(st *s,int newitem)
    {
        if(isfull(s)){
            printf("stack overflow");
        }
        else{
        s->top++;
        s->items[s->top]= newitem;
        
    }
    count++;
    }
    //remove
    void pop(st *s)
    {
        if(isEmpty(s)){
            printf("stack empty");
        }
        else
        {
            printf("Item popped=%d",s->items[s->top]);
            s->top--;
        }
        count--;
        printf("\n");
    }
    //printing
    void printstack(st *s) {
        printf("stack");
        for(int i=0;i<count;i++)
        {
            printf("%d",s->items[i]);
        }
        printf("\n");
    }
//driving code
int main(){
    int ch;
    st *s =(st *)malloc(sizeof(st));
    createEmptystack(s);
    push(s,1);
    push(s,2);
    push(s,3);
    push(s,4);
    printstack(s);
    pop(s);
    printf("in after pop");
    printstack(s);
    return 0;
}