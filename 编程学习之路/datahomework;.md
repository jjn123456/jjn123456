###### 1.**status CreateList_Dul(DuLinkList &L);**

```c
status CreateList_Dul(DuLinkList* L)
{
    L = (status)malloc(sizeof(DuLinkList));
    L->prior = NULL;
    L->next = NULL;
    L->data = 1;

    DuLinkList* rear = L;   
    //定义一个尾指针
    for(i=2;i<=N;i++){
        DuLinkList* node = (DuLinkList*)malloc(sizeof(DuLinkList));
        node->prior = NULL;
        node->next = NULL;

        rear->next = node;
        node->prior = rear;
        rear = node;
    }
    //循环结束的时候list就已经在末尾了
    //只需要连接尾指针和头指针
    L->prior = rear;
    rear->next = L;
    return L;
}
```

###### 2.status  GetElemP_Dul(DuLinkList L, int i);

###### 取得双向循环链表中第i个数据元素的位置指针

```c
status GetElemP_Dul(DuLinkList L, int i)
{
    Pmove = L;    //Pmove 指向首源节点
    for(int j=1;j<i;j++)
    {
        Pmove = Pmove->next;
    }
    return Pmove;
}
```

3.将单链表置逆

status ReverseList_L(LinkList &L);

```c
status ReverseList_L(LinkList &L)
{
    Pbehind = NULL;
    Pfront = NULL;
    Pthis = L;
    while(Pthis)
    {
        Pfront = Pthis->next
        Pthis->next = Pbehind;
        Pbehind = Pthis;
        Pthis = Pfront;
    }
    return Pthis;  //头节点    
}
```

4.

```c
设顺序表va中的数据元素递增有序。试写一算
法，将x插入到顺序表的适当位置上，以保持
该表的有序性。
Status InsertOrderList(SqList &va,ElemType x)
{
    int insertwhere = findIndex(va,x);
    int num = va.length+1;
    if(num>maxSize)
    {
        va.head = (Status*)realloc(va.head,(va.size+1)*sizeof(orderlist));
        if(insertwhere==va.length)
        {
            //顺序表已经满了,并且添加的元素最大，可以直接放在表尾\n
            va.head[va.length] = data;
            va.length++;
            return va;
        }
        else
        {
            //顺序表已经满了,添加的元素应该插入在第(insertwhere+1)个位置
            for (int i = va.length - 1; i >= insertwhere - 1; i--)
            {
                va.head[i + 1] = va.head[i];
            }
            va.head[insertwhere] = data;
            va.length++;
            return va;
        }
    }
    else
    {//表示顺序表一开始的长度够用
        if (insertwhere == va.length)
        {
            //顺序表没有满,添加的元素最大直接放在表尾
            va.head[va.length] = data;
            va.length++;
            return va;
        }
        else
        {
            //顺序表没有满,添加的元素应该插入在第insertwhere + 1个位置
            for (int i = va.length - 1; i >= insertwhere-1; i--)
            {
                va.head[i + 1] = va.head[i];
            }
            va.head[insertwhere] = data;
            va.length++;
            return va;
        }
    }
}

```

