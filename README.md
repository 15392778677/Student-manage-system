# Student-manage-system
- #### 实现功能：

1. 录入学生信息
2. 打印学生信息
3. 统计学生人数
4. 查找学生信息
5. 修改学生信息
6. 删除学生信息
7. 退出系统

- 运用的主要原理

  > 链表做存储机制
  >
  > 文本写入，读取，用文本文件当数据库
  >
  > 头文件的引用

- 运用的链表的几大功能

  > 链表的创建
  >
  > 链表的增删改查

- 清空文件，直接用只写"w"的形式打开，即可

  ```C
  //文本文件的清空
  //只需要用"w"打开即可，后来的内容会覆盖之前的内容，以实现数据库的更新
  	FILE* file=fopen("student.txt", "w");
  	while (t != NULL) {
  		fprintf(file, "%d  %s  %d\n", t->s.number, t->s.name, t->s.score);
  		t = t->next;
  	}
  	head = NULL;
  	fclose(file);
  	system("pause");
  	system("cls");
  }
  ```

- 让小黑框暂停，同时清理屏幕

  ```c
      system("pause");
  	system("cls");
  ```

- 头插法和尾插法，使链表实时增加

  ```c
  //头插法，Linklist*head=NULL;
  	Linklist* p=NULL;
      char ch='0';
  	while (1) 
      {
  		Linklist* node;
  		node = (Linklist*)malloc(sizeof(Linklist));
          
  		//头插法
          //先判断表头是否为空
  		if (p == NULL) {
  			p = node;
  			node->next = NULL;
  		}
  		else
  		{
  			node->next = p;
  			p = node;
  		}
          scanf("%d",&node->data);
          printf("还有吗？(y/n):");
  		scanf("%c", &ch);
          if (ch == 'y') 
  		{ 
  			continue;
  		}
  		else if (ch == 'n') break;
      }
  
  //尾插法
     Linklist* head,*tail,*node;
     head=(Linklist*)malloc(sizeof(Linklist));
     tail=head;
     while(1){
         node = (Linklist*)malloc(sizeof(Linklist));
         tail->next=node;
         tail=node;
         scanf("%d",&node->data);
          printf("还有吗？(y/n):");
  		scanf("%c", &ch);
          if (ch == 'y') 
  		{ 
  			continue;
  		}
  		else if (ch == 'n') break;
     }
  ```

  

