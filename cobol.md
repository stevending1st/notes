# Cobol

### Cobol 的哲学

### Cobol 的基础结构

Cobol程序是一种特殊的结构，既在列划分区域，又在行形成结构。
对于一行来说，前6列是是序号列（一般不编辑）；
第7列为标示列（注释符"*"、DEBUG行标识符"D"、字符串连接符"-"）;
第8列至11列为A区（包括部名、节名、层号）；
第12列至72列为B区（过程部的程序必须写在B区中）；
第72以后部分不能编辑。

### Hello WROLD
``` COBOL
```

##### 较全框架
``` Cobol
      *标识部
      *用于标识程序名，提供程序的一般性文档说明。
       IDENTIFICATION        DIVISION.
      *一般包含:
      *    程序名(PROGRAM-ID)プログラム ID、
       PROGRAM-ID.     HELLO.
      *    作成者(AUTHOR)、
      *AUTHOR.         STEVENDING1ST. 
      *    作成日(DATE-WRITTEN)等项。
      *DATE-WRITTEN.   19-04-08.
      *DATE-COMPILED.
      ****************************************************************** 
      *环境部 - 環境部「かんきょうぶ」
      *用于说明程序运行的环境，提供程序外部有关的项目。
       ENVIRONMENT           DIVISION.
      *配置节 
       CONFIGURATION         SECTION.
      *指定源计算机 
       SOURCE-COMPUTER.      ENTERPRISE-LINUX.
      *指定目标计算机
       OBJECT-COMPUTER.      ENTERPRISE-LINUX.
      *设置debug模式
      *SOURCE-COMPUTER.      ENTERPRISE-LINUX WITH DEBUGGING MODE.
       SOURCE-COMPUTER.       ENTERPRISE-LINUX.
      *指定读环境变量设置.
      *SPECIAL-NAMES.
      *环境变量名
      *ENVIRONMENT-NAME    IS  ENV-MANE.
      *环境变量值
      *ENVIRONMENT-VALUE   IS  ENV-VALUE.
      *输入输出节
      *INPUT-OUTPUT    SECTION
      ******************************************************************
      *数据部 - データ部
       DATA                  DIVISION.
      *文件节
      *FILE                  SECTION.
      *工作存储节
      *WORKING-STORAGE       SECTION.
      *COBOL变量定义需要加层号(表示层次关系)
      *层号依次排列顺序为:01，05，10，15，20，30 
      *连接节
      *子程序的参数的定义（只有文件为子程序时才需要定义）。
      *LINKAGE               SECTION.
      ******************************************************************
      *过程部 - 手続き部「てつづきぶ」
      *是程序的核心部分，它决定计算机应进行什么操作。
       PROCEDURE             DIVISION.
      *每个程序一般分为五大节
      *MAIN-RTN：各主要程序节间的调用
       MAIN-RTN              SECTION.
      *    开始处理
           PERFORM INIT-RTN.   
      *    主处理
           PERFORM MAIN-PROC-RTN.
      *    处理结束
           PERFORM END-RTN.    
           STOP    RUN.
       MAIN-EXT.
           EXIT.
      *-----------------------------------------------------------------
      *INIT-RTN（前处理、開始処理）：初始化变量,设定初始值等 
       INIT-RTN              SECTION.
       INIT-EXT.
           EXIT.
      *-----------------------------------------------------------------
      *MAIN-PROC-RTN（主处理、メイン処理）：程序业务处理部分
       MAIN-PROC-RTN         SECTION.
           DISPLAY "THIS IS A COBOL PROGRAM".
      *-----------------------------<DEBUG>-----------------------------
      D    DISPLAY "THIS IS A COBOL PROGRAM OF DEBUG".
      *-----------------------------------------------------------------
       MAIN-PROC-EXT.
           EXIT.
      *-----------------------------------------------------------------
      *END-RTN（后处理、正常終了処理）：程序正常结束时的出口
       END-RTN              SECTION.
       END-EXT.
           EXIT.
      *-----------------------------------------------------------------
```

##### 基础框架
``` Cobol
``` Cobol
      *标识部
      *用于标识程序名，提供程序的一般性文档说明。
       IDENTIFICATION        DIVISION.
      *一般包含:
      *    程序名(PROGRAM-ID)プログラム ID、
       PROGRAM-ID.     HELLO.
      *    作成者(AUTHOR)、
      *AUTHOR.         STEVENDING1ST. 
      *    作成日(DATE-WRITTEN)等项。
       DATE-WRITTEN.   19-04-08.
       DATE-COMPILED.
      ****************************************************************** 
      *环境部 - 環境部「かんきょうぶ」
      *用于说明程序运行的环境，提供程序外部有关的项目。
       ENVIRONMENT           DIVISION.
      *配置节 
       CONFIGURATION         SECTION.
      *指定源计算机 
       SOURCE-COMPUTER.      ENTERPRISE-LINUX.
      *设置debug模式
      *SOURCE-COMPUTER.      ENTERPRISE-LINUX WITH DEBUGGING MODE.
      ******************************************************************
      *数据部 - データ部
       DATA                  DIVISION.
      *工作存储节
      *WORKING-STORAGE       SECTION.
      *COBOL变量定义需要加层号(表示层次关系)
      *层号依次排列顺序为:01，05，10，15，20，30 
      ******************************************************************
      *过程部 - 手続き部「てつづきぶ」
      *是程序的核心部分，它决定计算机应进行什么操作。
       PROCEDURE             DIVISION.
      *每个程序一般分为五大节
      *MAIN-RTN：各主要程序节间的调用
       MAIN-RTN              SECTION.
      *    开始处理
           PERFORM INIT-RTN.   
      *    主处理
           PERFORM MAIN-PROC-RTN.
      *    处理结束
           PERFORM END-RTN.    
           STOP    RUN.
       MAIN-EXT.
           EXIT.
      *-----------------------------------------------------------------
      *INIT-RTN（前处理、開始処理）：初始化变量,设定初始值等 
       INIT-RTN              SECTION.
       INIT-EXT.
           EXIT.
      *-----------------------------------------------------------------
      *MAIN-PROC-RTN（主处理、メイン処理）：程序业务处理部分
       MAIN-PROC-RTN         SECTION.
           DISPLAY "THIS IS A COBOL PROGRAM".
      *-----------------------------<DEBUG>-----------------------------
      D    DISPLAY "THIS IS A COBOL PROGRAM OF DEBUG".
      *-----------------------------------------------------------------
       MAIN-PROC-EXT.
           EXIT.
      *-----------------------------------------------------------------
      *END-RTN（后处理、正常終了処理）：程序正常结束时的出口
       END-RTN              SECTION.
       END-EXT.
           EXIT.
      *-----------------------------------------------------------------
```

##### 基础框架（无注释）
``` Cobol
       IDENTIFICATION        DIVISION.
       PROGRAM-ID.     HELLO.
      *AUTHOR.         STEVENDING1ST. 
       DATE-WRITTEN.   19-04-08.
       DATE-COMPILED.
      ****************************************************************** 
       ENVIRONMENT           DIVISION.
       CONFIGURATION         SECTION.
       SOURCE-COMPUTER.      ENTERPRISE-LINUX.
      *SOURCE-COMPUTER.      ENTERPRISE-LINUX WITH DEBUGGING MODE.
      ******************************************************************
       DATA                  DIVISION.
      *WORKING-STORAGE       SECTION.
      ******************************************************************
       PROCEDURE             DIVISION.
       MAIN-RTN              SECTION.
      *    开始处理
           PERFORM INIT-RTN.   
      *    主处理
           PERFORM MAIN-PROC-RTN.
      *    处理结束
           PERFORM END-RTN.    
           STOP    RUN.
       MAIN-EXT.
           EXIT.
      *-----------------------------------------------------------------
       INIT-RTN              SECTION.
       INIT-EXT.
           EXIT.
      *-----------------------------------------------------------------
       MAIN-PROC-RTN         SECTION.
           DISPLAY "THIS IS A COBOL PROGRAM".
      *-----------------------------<DEBUG>-----------------------------
      D    DISPLAY "THIS IS A COBOL PROGRAM OF DEBUG".
      *-----------------------------------------------------------------
       MAIN-PROC-EXT.
           EXIT.
      *-----------------------------------------------------------------
       END-RTN              SECTION.
       END-EXT.
           EXIT.
      *-----------------------------------------------------------------
```

### 基本语法

##### 赋值语句
- 将一个变量赋给另个变量
```
           MOVE  A   TO    B.
```
- 将一个变量同时赋给另外两个变量。
```
           MOVE  A   TO    B   C .
```
- 将一个变量全部赋为某个字符
```
           MOVE  ALL  “X”   TO  A.
```
- 程序可以操作一个变量的局部. 
```
           A(START:LENGTH)
      *eg: 将变量A第2位开始10长度的内容全赋为字符”X”
           MOVE  ALL  “X”   TO  A(2:10).
```
注意： 
-  对于赋值溢出，截取的方式为：
     - 字符型变量截去右边的溢出部分。 
     - 数值型变量截去整数部高位、小数部低位的溢出部分。
-  组合项传送，它们的数据结构必须相同。

#### 接收语句
控制台接收一个值，存储到标识符变量。
``` cobol
       ACCEPT 标识符.
```

##### 显示语句DISPLAY
向控制台打印显示的信息
``` cobol
           DISPLAY  “DISPLAY  RESULT：”  STR-1  “@@”.
```
注意：
- 如果程序基于opentp1环
  境,该信息将写到opentp1的log文件中；
- 打印内容可连接，内容之间中间空格即可。
- 字符串加引号，变量直接输入变量名。
- 打印组合项项名时，打印子项目内容。

##### 接受语句
接受从控制台上的输入值（将控制台输入的值存储到已定义的变量）。
``` Cobol
         ACCEPT   WK-A.
```

##### 算术运算语句
```cobol
      *B=A+B,A也可以为值。
           ADD A TO B.
      *C=A+B+C,A,B也可以为值。
      *-逗号可以省略，空格不可以省略。
      *-C后面也可以跟多个值。
           ADD A, B TO C.
      *C=A+B,A,B也可以为值。
      *-逗号可以省略，空格不可以省略。
      *-C后面也可以跟多个值。
           ADD A, B GIVING C.    
```

```
```




```
      *环境部
       ENVIRONMENT       DIVISION.
      *输入输出节
       INPUT-OUTPUT      SECTION.
      *文件控制节
       FILE-CONTROL.
           SELECT 内部文件名 ASSSIGN TO 外部文件名。
         
      *IN-FILE 文件名标识
       SELECT  IN-FILE   ASSIGN
      * './IN_FILE.dat' 文件地址
                './IN_FILE.dat'
      * IN-ST 文件状态标识
      * 00 正常 ；  10 读到最后
                FILE    STATUS  IS  IN-ST
      *
                ORGANIZATION    IS  LINE    SEQUENTIAL
```

```
      * 声明
       FD  IN-FILE     RECORD  CONTAINS    46     CHARACTERS.
       01  IN-FILE-REC.
           COPY   “FILE1.cpy”.
```
```
       FD  OUT-FILE.
       01  OUT-FILE-REC            PIC X(78).

```
打开IN-FILE指定的文件
```
       OPEN    INPUT              IN-FILE.
```
打开OUT-FILE指定的文件
```
       OPEN    OUTPUT             OUT-FILE.
```

```
       READ    IN-FILE
           AT      END
               MOVE    CNS-EOF    TO  FLG-SYR-END
           NOT AT  END
               ADD     CNS-INC-1  TO  CNT-READ-IN-FILE
       END-READ.

```

```
       MOVE    WK-OUT-FILE        TO OUT-FILE-REC.
       WRITE   OUT-FILE-REC
       END-WRITE.
```

```
       CLOSE                      IN-FILE.
```





INITIALIZE  初期化

FUNCTION CURRENT-DATE 取当前日期（8位），eg(02190411)