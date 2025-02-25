# 範例學習C 程式設計
```
本單元規劃以 範例  快速引導 學生 掌握 基礎 C 程式語法

更多完整內容仍需參考學習資源或買書學習
```

[階段式學習C程式設計 綱要](階段式學習C程式設計.md)

## 練習看看 底下程式
```
C 語言經典100例
https://www.runoob.com/cprogramming/c-100-examples.html
```
```
有興趣的同學也可以 參加 
APCS-大學程式設計先修檢測
https://apcs.csie.ntnu.edu.tw/

TOI 臺灣國際資訊奧林匹亞競賽
Taiwan Olympiad in Informatics
請參考網站說明 https://toi.csie.ntnu.edu.tw/
```

```
持續編修中
```
```
給講師的話 ==> 可以使用線上編譯 加快講解

https://www.onlinegdb.com/online_c_compiler
```
## A.基礎 C 程式設計
```
1 輸出與輸入
   格式化的輸出與輸入
2.基本資料型態  ==> 進階型資料結構
   數值型資料型態
   字串或字元型資料型態
3.運算子、運算式與敘述
4.選擇性敘述 if   switch
5.迴圈 for   while     do.. while
6.函數
    遞迴函數
7.陣列(不使用指標)
8.字串(字元陣列)與字串處理(不使用指標)
```
# 1.輸出入
```
#include <stdio.h>
 
/* 單行註解 comment */

/* 
 多行註解 comment
 多行註解 comment
 多行註解 comment
 */

int main()
{
    printf("Hello, CTFer! \n"); //第二種單行註解 comment
    return 0;
}
```
```
https://pydoing.blogspot.com/2010/07/c-stdio.html
```
```
C 語言把所有的設備（比如顯示器、鍵盤）都當作檔案。
所以設備處理的方式與檔案（比如顯示器、鍵盤）相同。
標準輸入 ==	stdin  ==  鍵盤
標準輸出 == stdout ==  螢幕
標準錯誤 == stderr ==  螢幕

接收鍵盤的輸入 與 將結果輸出到螢幕 等處理函數(方法)都是定義在stdio.h標頭檔

stdio.h 是一個標頭檔[header] 定義許多標準輸入輸出的處理函示(function)

#include 是一個預處理命令(directive)，可用来導入|載入標頭檔文件。 

當編譯器在編譯過程中遇到 printf() 函數時，如果沒有找到 stdio.h 標頭檔，會發生編譯錯誤。

https://pydoing.blogspot.com/2010/07/c-stdio.html
```
## 基本輸出與輸入 ==>  printf(), scanf()

## 錯誤程式更正題
```
底下為錯誤的程式實作題
原題要你輸入如底下的執行成果

請輸入一個數字 : 1.2                                                                                              
你剛剛輸入的數字是 : 1.200000                                                                                     
你剛剛輸入的數字 平方後答案是 : 1.440000 

請更正之
```
#### 錯誤的程式
```
#include<stdio.h>
#include<math.h>
 
int main()
{
    int num,result;
 
    printf("請輸入一個數字 : ");
    scanf("%f",&num);
    printf("你剛剛輸入的數字是 : %f",num);
    //result = pow(num, 2);
    //printf("你剛剛輸入的正整數 平方後答案是 : %f", result);
}
```
```
把  int num,result; 改成 float num,result; 

http://tw.gitbook.net/c_standard_library/c_function_pow.html
```
## 【字元】的輸出與輸入 ==> getchar(), putchar()
```
#include <stdio.h>
 
int main( )
{
   int c;
 
   printf( "Enter a value :");
   c = getchar( );
 
   printf( "\nYou entered: ");
   putchar( c );
   printf( "\n");
   return 0;
}
```
## 【字串】的輸出與輸入  ==> gets(),  puts()
```
#include <stdio.h>
 
int main( )
{
   char str[100];
 
   printf( "Enter a value :");
   gets( str );
 
   printf( "\nYou entered: ");
   puts( str );
   return 0;
}
```
## 格式化輸出
```
%c：以字元方式輸出

%d：10 進位整數輸出
%o：以 8 進位整數方式輸出
%x、%X：將整數以 16 進位方式輸出

%u：無號整數輸出
%lu：long unsigned 型態的整數

%f：浮點數輸出
%e、%E：使用科學記號顯示浮點數
%g、%G：浮點數輸出，取 %f 或 %e（%f 或 %E），看哪個表示精簡
%%：顯示 %


%s：字串輸出

%p：指標型態 
```
## 範例
```
#include <stdio.h>

int main(void) {
    printf("ASCII 編碼與解碼 初初階\n");
    printf("顯示字元 %c\n", 'A');
    printf("顯示為十進位整數 %d\n", 'A');
    printf("顯示為八進位整數 %o\n", 'A');
    printf("顯示為十六進位整數 %X\n", 'A');
    printf("顯示為十六進位整數 %x\n", 'A');
    
   // printf("顯示為科學記號 %E\n", 0.001234);    
   // printf("顯示為科學記號 %e\n", 0.001234);    

    return 0;
}
```
## 甚麼? format 格式化輸出 可以 發生漏洞? Format string Vuln.
```
請參加 PWN-CTF 進修
```
# 2.基本資料型態 
```
   數值型資料型態
   字串或字元型資料型態

資料型態：
char    字元==>'Z'、'21'與 '&'等

int	整數
long	長整數
short      短整數

float	單精度浮點數
double	倍精度浮點數
```
# 3.運算子、運算式與敘述
# 變數
```
變數的命名規則 
1.變數名稱可以是英文字母、數字或底線
2.名稱中不能有空白字元
3.第一個字元不能是數字
4.不能使用到關鍵字
```
### 範例小考[複選題]
```
下列何者是正確的變數名稱?
(A)if  (B)intel_9x (C) _AMD (D)2dos (E)my dogs (F)goto
```
### 使用變數....
```
int num; 	   /* 宣告 num 為整數變數 */
int x,y,z;      /* 同時宣告 x,y 與 z 為整數變數 */
float total=0.0;  /* 宣告浮點數變數total，並設值為0.0 */
```
## 請上網找資料 舉例說明底下的運算
```
https://www.runoob.com/cprogramming/c-operators.html
算術運算子
關係運算子
邏輯運算子
位運算子
設定運算子
雜項運算子
```
## 範例
```
#include <stdio.h>
 
int main()
{
   int a = 21;
   int b = 10;
   int c ;
 
   c = a + b;
   printf("加法測試的值是 %d\n", c );
   c = a - b;
   printf("減法測試的值是 %d\n", c );
   c = a * b;
   printf("乘法測試的值是 %d\n", c );
   c = a / b;
   printf("除法測試的值是 %d\n", c );
   c = a % b;
   printf("模運算測試的值是 %d\n", c );
   c = a++;  
   printf("a的值是 %d\n", a);
   printf("c的值是 %d\n", c );
   c = a--;  
   printf("a的值是 %d\n", a);
   printf("c的的值是 %d\n", c );
   c = ++a;  
   printf("a的值是 %d\n", a);
   printf("c的值是 %d\n", c );
   c =a++ + ++a;  
   printf("a的值是 %d\n", a);
   printf("c的值是 %d\n", c );
}
```
```
加法測試的值是 31
減法測試的值是 11
乘法測試的值是 210
除法測試的值是 2
模運算測試的值是 1
a的值是 22
c的值是 21
a的值是 21
c的的值是 22
a的值是 22
c的值是 22
a的值是 24
c的值是 46
```
# 4.選擇性敘述 ==> 各類型 if   switch
## if
```
#include<stdio.h>
 
int main()
{
    int num;
 
    printf("請輸入一個正整數 : ");
    scanf("%d",&num);
 
    if (num%2==0)
      printf("你輸入的偶數");
}
```
## if ..else ..
```
#include<stdio.h>
 
int main()
{
    int num;
 
    printf("請輸入一個正整數 : ");
    scanf("%d",&num);
 
    if (num%2==0)
      printf("你輸入的偶數\n");
    else
      printf("你輸入的奇數\n");
}
```
## ? : 運算子(三元運算子)
```
#include<stdio.h>
 
int main()
{
    int num;
 
    printf("請輸入一個正整數 : ");
    scanf("%d",&num);
 
    (num%2==0)?printf("偶數"):printf("奇數");
}
```

## 範例: C 命令列參數(command-line arguments)
```
#include <stdio.h>

int main( int argc, char *argv[] )  
{
   if( argc == 2 )
   {
      printf("The argument supplied is %s\n", argv[1]);
   }
   else if( argc > 2 )
   {
      printf("Too many arguments supplied.\n");
   }
   else
   {
      printf("One argument expected.\n");
   }
}
```
## switch==> 執行底下程式 說明其結果為何會如此呈現? 
```
#include <stdio.h>
 
int main ()
{
   /* 區域變數定義 */
   char grade = 'B';
 
   switch(grade)
   {
   case 'A' :
      printf("很棒！\n" );
      //break;
   case 'B' :
   case 'C' :
      printf("做得好\n" );
      //break;
   case 'D' :
      printf("您通過了\n" );
      //break;
   case 'F' :
      printf("最好再試一下\n" );
      //break;
   default :
      printf("無效的成績\n" );
   }
   printf("您的成績是 %c\n", grade );
 
   return 0;
}
```
```
將 //break ==> 去掉// ==> 執行後答案有何不同?
```
# 5.迴圈 
```
for   
while     
do.. while
```
## for loop(迴圈)  ==> 計算n!
```
#include <stdio.h>

int main(void)
{
	int n;
	int total = 1;
	int i;

	scanf("%d", &n);

	for(i = 1; i <= 10; i++)
		total *= i;

	printf("the result is %d\n", total);

	return 0;
}
```
## while loop ==> 計算n!
```
#include <stdio.h>

int main(void)
{
	int n;
	int mul = 1;
	int i;

	scanf("%d", &n);
	
	i = 1;
	while(i <= n)
	{
		mul *= i;
		i++;
	};

	printf("the result is %d\n", mul);

	return 0;
}
```
## do ..while .. ==> 計算n!
```
//do_while
#include <stdio.h>

int main(void)
{
	int n;
	int mul = 1;
	int i;

	scanf("%d", &n);
	
	i = 1;
	do{
		mul *= i;
		i++;
	}while(i <= n);

	printf("the result is %d\n", mul);

	return 0;
}
```
# 6.函數

```
#include <stdio.h>
 
int ifactorial(int z)
{
	int mul = 1, i = 1;
	while(i <= z)
	{
		mul *= i;
		i++;
	};
	return mul;
}

int  main()
{
    int i = 4;
    printf("%d 的階乘為%d\n", i, ifactorial(i));
    return 0;
}
```

## 遞迴函數 ==> 計算n!
```
#include <stdio.h>
 
double factorial(unsigned int i)
{
   if(i <= 1)
      return 1;
   else   return i * factorial(i - 1);
}

int  main()
{
    int i = 15;
    printf("%d 的階乘為%f\n", i, factorial(i));
    return 0;
}
```

### 作業: 
```
費氏數列:遞迴方法 vs iterative ==> 再算　時間複雜度
費氏數列值第1及第2 項皆為1，
第3項之後的公式為f(n)= f(n-1) + f(n-2)。

1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233

使用者輸入一個正整數X，計算出費氏數列的第X項並輸出。

計算費氏數列的第X項，請輸入X= 12  
==>  費氏數列的第12項= 144

(1)請使用靜態遞迴方法算出費氏數列。
(2)請使用 iterative方法算出費氏數列。
```
# 7.陣列(不使用指標) ==> 使用索引(index) 存取陣列資料
```
#include <stdio.h>
 
int main ()
{
   int n[ 10 ]; /* n 是一個包含 10 個整數的陣列 */
   int i,j;
 
   /* 初始化陣列元素 */         
   for ( i = 0; i < 10; i++ )
   {
      n[ i ] = i + 100; /* 設置元素 i 為 i + 100 */
   }
   
   /* 輸出陣列中每個元素的值 */
   for (j = 0; j < 10; j++ )
   {
      printf("Element[%d] = %d\n", j, n[j] );
   }
 
   return 0;
}

```
# 8.字串(字元陣列)與字串處理(不使用指標)

## 範例
```
#include <stdio.h>
#include <string.h>
 
int main ()
{
   char str1[9] = "CTFer";
   char str2[9] = "hacker";
   char str3[9];
   char str4[9];
   int  len ;
 
   /* 複製 str1 的內容複製到 str3 */
   strcpy(str3, str1);
   printf("strcpy( str3, str1) :  %s\n", str3 );
 
   /* 連接 str1 和 str2後的結果 存到str1 */
   strcat( str1, str2);
   printf("strcat( str1, str2):   %s\n", str1 );
 
    /* 連接 str2 和 str1後的結果 存到str1   */
   strcat( str2, str1);
   printf("strcat( str2, str1):   %s\n", str2 );
   
   /* 連接後，str1 的總長度 */
   len = strlen(str1);
   printf("strlen(str1) :  %d\n", len );
 
   strcpy(str4, str1);
   printf("strcpy( str4, str1) :  %s\n", str3 );
   str4[3] = '\0';
   printf(str4);
   
   return 0;
}
```
```
https://www.onlinegdb.com/online_c_compiler 

執行結果
main.c:38:11: warning: format not a string literal and no format arguments [-Wformat-security]    
    printf(str4 );                                                                                
           ^~~~                                                                                   
strcpy( str3, str1) :  CTFer                                                                      
strcat( str1, str2):   CTFerhacker                                                                
strcat( str2, str1):   erCTFerhacker                                                              
strlen(str1) :  22                                                                                
strcpy( str4, str1) :  cker                                                                       
*** stack smashing detected ***: ./a.out terminated                                               
CTFAborted (core dumped)    
```

## 修正後的程式
```
#include <stdio.h>
#include <string.h>
 
int main ()
{
   char str1[9] = "CTFer";
   char str2[9] = "hacker";
   char str3[9];
   char str4[9];
   int  len ;
 
   /* 複製 str1 的內容複製到 str3 與str 4 */
   strcpy(str4, str1);
   strcpy(str3, str1);
   printf("strcpy( str3, str1) :  %s\n", str3 );
 
   /* 連接 str1 和 str2後的結果 存到str1 */
   strcat( str1, str2);
   printf("strcat( str1, str2):   %s\n", str1 );
 
    /* 連接 str2 和 str1後的結果 存到str1   */
   //strcat( str2, str1);
   //printf("strcat( str2, str1):   %s\n", str2 );
   
   /* 連接後，str1 的總長度 */
   len = strlen(str1);
   printf("strlen(str1) :  %d\n", len );
 
   printf("strcpy( str4, str1) :  %s\n", str4 );
   str4[3] = '\0';
   printf("處理過的字串變成(請說明why?) :  %s\n",str4);
   
   return 0;
}
```
