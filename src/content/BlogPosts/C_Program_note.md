---
title: "C notes"
date: "2025-09-01"
tags: ["notes", "astro"]
excerpt: "有關C 的學習筆記"
---
# C Program note

## typedef

使用時機大多是為了減少打字時間，例如說：" unsigned int typedef_Name ; " 在某個程式碼中經常被使用到，重複 unsigned char 打這些字也是蠻花時間的 (雖然有自動補齊可以使用～)，

可以用 typedef 來自定自己所需型別以減少key in時間。

與基本型別，short, int, long, float, double, char 等等型別用法一樣，

都是告訴C說我有個變數，型別是什麼，變數名字叫什麼，內容物是什麼。

```c
//用 unsigned int   為例

typedef unsigned int typedef_Name;
//在程式碼中就能使用 typedef_Name 他會自動幫你變數做好 unsigned int 的動作
typedef_Name   Variable_name  =   UINT_MAX;

//example

#include <stdio.h>
#include <limits.h>

typedef unsigned int un_Int; // 建立一個名為 un_Int 的型別其功能就是 不帶符號的整數型別
int main (void){
  // INT 的範圍值為 -2147483648 ~ 2147483647
	// 不帶符號的INT範圍值 0 ~ 4294967295
	int x = INT_MAX;
	un_Int ux = UINT_MAX;
	
	printf("x = %d", x);
	printf("ux = %u", ux);  // ％u是不帶符號的輸出，如果使用％d 你會拿到-1
	printf("x+1 = %d", x+1);
	printf("ux+1 = %u", ux+1);
}
```

## struct

結構

```c
#include <stdio.h>
#include <cs50.h>
#include <string.h>

typedef struct  person ps;
struct  person
{
    string name;
    string numbers;
};

int main(void)
{
    ps people[2];
    people[0].name = "Brian";
    people[0].numbers = "0912345678";
    people[1].name = "David";
    people[1].numbers = "0987654321";
    
    for (int i=0 ; i<2 ; i++){
        if (strcmp(people[i].name, "David") == 0){
            printf("Found numbers: %s\n", people[i].numbers);
            return 0;
        }
    }
    printf("Not Found.\n");
    return 1;
}
```