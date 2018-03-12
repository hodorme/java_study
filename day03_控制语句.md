## 一. switch 语句

1. **格式**

   ```java
   switch(值){
   	case 值1:	
   		//语句体1;
   		break;
   	case 值2:		
   		//语句体2;
   		break;
   	//......
   	default:
   		//语句体3;
   		break;
   }
   ```

2. **执行流程**

   * 先看switch括号中的值
   * 然后和case后面的值匹配, 如果有就执行这个case后面的语句, 否则执行default 控制的语句

3. **注意事项**

   * case后面只能是常量, 不能是变量, 多个case后面不能出现相同的值
   * switch后面的值的类型只能是byte, short ,int ,字符, 字符串 , 枚举
   * 结束条件: 执行到break , 或者代码运行完毕结束,如果一直遇不到break就会一直执行
   * defautl 可以省略, 但是建议不要省略

4. **演示**

   ```java
   public static void main(String[] args) {
   	//输入数值,打印对象的星期数
   	int week = 5;
   	switch (week) {
   		case 1:
   			System.out.println("星期一");
   			break;
   		case 2:
   			System.out.println("星期二");
   			break;
   		case 3:
   			System.out.println("星期三");
   			break;
   		case 4:
   			System.out.println("星期四");
   			break;
   		case 5:
   			System.out.println("星期五");
   			break;
   		case 6:
   			System.out.println("星期六");
   			break;
   		case 7:
   			System.out.println("星期七");
   			break;
   		default:
   			System.out.print("您的输入有误");
   			break;
   	}
   	
   }
   ```

5. **case穿透**

   * 当程序执行某个case后的代码,但是没有遇到break的时候, 就会一直执行下面的所有可执行的语句 

   ```java
   public static void main(String[] args) {
   	
   	int week = 1;
   	switch (week) {
   		case 1:
   			System.out.println("语句1......");
   			
   		case 2:
   			System.out.println("语句1......");
   			
   		case 3:
   			System.out.println("语句1......");
   			break;
   		default:
   			System.out.print("其他情况");
   			break;
   	}
   	
   }
   ```

6. **测试题**

   * 使用switch语句改写判断学生成绩的等级

## 二. 循环语句

1. **定义**
   * 满足一定的条件下, 可以重复执行的语句
   * 循环语句可以帮助我们用很少的代码执行大量的工作
2. **分类**
   * for 循环 
   * while 循环
   * do...while

## 三. for 循环语句

1. **格式**

   ```java
   for (初始化表达式; boolean;循环后表达式) {
   	//执行语句
   }
   ```

2. **执行流程**

   * 执行初始化语句
   * 执行判断条件 , 看其返回值是true还是false
     * 如果是true ,就执行循环体
     * 如果是false , 就结束循环
   * 循环体执行到最后, 执行循环后表达式
   * 再次执行判断条件, 重复第二步

3. **注意事项**

   * 循环前表达式 : 在循环开始前执行, 无论循环多少次, 这个表达式只执行一次
   * 关系表达式 :  无论是简单还是复杂 , 其结果必须是boolean
   * 循环后表达式 : 在每次循环体执行完毕之后执行
   * 循环体如果只有一句话, 大括号可以省略, 建议不要省略

4. **演示**

   * 输出10次HelloWorld

   ```java
   public static void main(String[] args) {
   	
   	for (int i = 0; i < 10; i++) {
   		System.out.println("HelloWorld");
   	}
   }
   ```

5. **测试题**

   * 在控制台输出所有的”水仙花数”
   * 所谓的水仙花数是指一个三位数，其各个位数字的立方和等于该数本身
     * 举例：153就是一个水仙花数
     * 153 = 1\*1\*1 + 5\*5\*5 + 3\*3\*3 = 1 + 125 + 27= 153

6. **测试题2**

   * 一张纸的厚度是0.2mm, 多少张纸叠加可以达到朱穆拉马峰的高度(8848.13米)

7. **测试题3**

   * 计算一个整数阶乘的结果
     * 举例 :  5的阶乘是 1\*2\*3\*4\*5 = 120

## 四. while 循环语句

1. **格式**

   ```java
   while( boolean ){
   	循环语句;
   	控制语句;
   }
   ```

2. **执行流程**

   * 执行判断语句 , 看其返回值是true还是false
     * 如果是true ,就继续执行
     * 如果是false, 结束循环
   * 执行循环体
   * 执行控制条件语句
   * 返回第一步继续执行

3. **演示**

   * 计算1到100的和

   ```java
   public static void main(String[] args) {
   	
   	int i = 1;		//相当于for循环的初始化表达式
   	int sum = 0;
   	while (i <= 100) {
   		sum += i;
   		i++;
   	}
   	System.out.println(sum);
   }
   ```

4. **注意事项**

   * 我们一般可以将while循环看作是for循环的简写格式
   * 使用的时候一般都用在循环的次数不明确的情况下
   * 控制条件语句也属于循环语句

5. **测试题**

   * 求出1到100中所有偶数的和

## 五. do...while 循环语句

1. **格式**

   ```java
   do {
   	循环语句;
   	控制条件语句;
   } while ( boolean );
   ```

2. **执行流程**

   * 执行循环体语句
   * 执行控制条件语句
   * 执行判断条件语句,看其返回值是true还是false
     * 如果是true , 就继续执行执行循环体
     * 如果是false, 就结束循环

3. **演示**

   ```java
   public static void main(String[] args) {
   	int i = 0;
   	do {
   		System.out.println("HelloWorld");
   		i++;
   	} while (i>0);

   }
   ```

4. **注意事项**

   * do..while循环无论条件是否成立循环体都会执行一次

## 六. 循环结构的总结

1. 注意事项
   * do....while 循环至少执行一次循环体
   * for , while 循环必须先判断条件是否成立,然后决定是否执行循环体语句
   * 如果你想在循环结束后继续使用控制条件的那个变量 , 用while语句比较好
   * 注意控制条件 , 避免造成死循环
2. 死循环
   - while(true){...}
   - for(;;){...}

## 七. 关键字的使用

1. **return** 

   * 可以写在方法体的任意地方
   * 是和方法打交道的
   * 结束整个方法, 之后的代码全部都不再执行

   ```java
   public static void main(String[] args) {
   	//循环任意区间内的整数, 当找到7的倍数的时候终止整个方法
   	//如果没有找到的话, 提示没有扎到
   	int i = 10;
   	int b = 100;
   	for(;i<=b;i++){
   		if(i%7==0){
   			System.out.println("找到7的倍数:"+i);
   			return;
   		}
   	}
   	System.out.println("没有找到");
   }
   ```


2. **break**

   * 用在循环中或者switch语句中
   * 终止并跳出循环或者结束switch语句

   ```java
   public static void main(String[] args){
   	for(int i=0;i<3;i++){  
           System.out.println("break之前的语句"); 
           if(i==1){  
               //忽略本次循环剩下的语句  
               break;  
           }  
           System.out.println("break之后的语句");  
       } 
   }
   ```

3. **continue**

   * 终止本次循环,继续下次循环, 这次循环中continue之后的代码都在不在执行

   ```java
   public static void main(String[] args) {
   	
   	for(int i=0;i<3;i++){  
           System.out.println("i的值是"+i);  
           if(i==1){  
               //忽略本次循环剩下的语句  
               continue;  
           }  
           System.out.println("continue之后的语句");  
       } 
   }
   ```

4. **break , continue 可用于父循环, 给父循环起别名**

   ```java
   public static void main(String[] args) {
   	
    w:	for (int i = 0; i < 10; i++ ) {
   		//外循环语句
   	 	System.out.println("外循环语句.....前");
   		for (int j = 0; j < 10; j++) {
   			break w;
   		}
   		System.out.println("外循环语句.....后");
   	}
   }
   ```

5. **测试题**

   * 模拟用户登录 , 提示用户输入用户名和密码, 和本地的数据进行比对,如果成功提示登录成功, 否则提示失败,然后询问用户是否再次输入

## 八. 循环嵌套

1. **定义**

   * 有的时候一个循环是无法完成需求的,这时我们就可以将多个循环嵌套使用

2. **九九乘法表**

   ```java
   public static void main(String[] args) {
   	//外循环控制行
   	for (int i = 1; i <= 9; i++) {
   		//内循环控制列
   		for (int j = 1; j <= i; j++) {
   			//不换行打印  用制表符来修饰列
   			System.out.print(j+"*"+i+"="+(j*1)+"\t");
   		}
         	//打印换行
   		System.out.println();
   	}
   }
   ```

## 作业

1. **第二题**
   * 求出0-100中所有奇数的和
2. **第三题**
   * 从键盘录入整数, 如果是1 ,打印 "学习java" , 如果是2, 打印"睡觉" , 如果是3,终止程序, 如果是其他数, 继续循环
3. **扩展题**
   * 使用 * 打印等腰三角形
4. **扩展题**
   * 使用* 打印菱形