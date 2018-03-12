## 一. 函数(方法)

1. **定义**

   * java中的运行代码除极个别情况外,必须写在方法中, 方法就是代码的载体
   * 我们平时写代码的main方法也是一个方法,只是比较特殊而已, 可以被jvm识别
   * 因为要适应不同的需求, 我们的方法也是千变万化的. 一个main方法显然是无法达到我们的要求的
   * 当我们用代码定义了一个功能, 想要将功能保存下来沿用,就必须要以方法为载体
   * 方法的出现提升了代码的复用性


2. **格式**

   ```java
   修饰符 静态/非静态 返回值类型 方法名(参数类型 参数名1,参数类型 参数名2...) {
   	//方法体语句;
   	return 返回值; 
   }
   ```

3. **格式详解**

   * 修饰符 : 设定方法的作用范围, 现阶段只要用public就可以了
   * 静态/非静态 : static关键字表示静态 , 出现static , 这个方法就是静态方法,没有就是非静态
   * 返回值类型 : 就是代码运行的结果的数据类型
   * 方法名 : 这个方法的名称, 调用的时候我们使用的就是方法名
   * 参数 : 
     * 实际参数 : 就是实际参加运算的值 , 基本数据类型就是值, 引用数据类型是地址值
     * 形式参数 : 定在在方法上, 用来表示接收的数据的类型
   * 参数名 : 就是变量名
   * 方法体语句 : 方法中的功能代码, 也是我们实际运行的代码
   * return : 关键字, 表示结束方法, 同时可以返回一个值
   * 返回值 : 就是功能的运行的结果, 由return带给调用者

4.  **演示**

   ```java
   public static void main(String[] args) {
   	//调用计算两个数乘积的方法
   	int c = multipy(14, 15);
   	System.out.println(c);
   }
   //定义方法,计算两个数的乘积
   public static int multipy(int a, int b){
   	int count = a * b;
   	
   	return count;
   }
   ```

5. **分类**

   * 有参方法
   * 无参方法
   * 有返回值
   * 无返回值

   ```java
   //无参无返回值的方法
   public static void method1(){
   	System.out.println("我就是自娱自乐");
   }	
   //有参无返回值的方法
   public static void method2(int a){
   	//计算a平方 
   	System.out.println(a*a);
   }	
   //无参有返回值的方法
   public static long method3(){
   	//获取当前时间
   	long time = System.currentTimeMillis();
   	return time;
   }
   //有参有返回值
   public static int method4(int a,int b){
   	//返回a,b中数值较大的那个
   	return a>b?a:b;
   }
   ```

6. **调用方式**

   * 单独调用 方法独立于其他代码, 独立执行功能
     * 多用检测维护型的方法
   * 输出调用 只做结果输出, 这种调用对我们来说没有任何意义
   * 赋值调用 有返回值结果, 可以进一步操作返回值

   ```java
   public static void main(String[] args) {
   	//赋值调用
   	int c = multipy(14, 15);
   	System.out.println(c);
   	
   	//输出调用
   	print();
   	
   	//单独调用
   	clear();
   }
   //定义方法,计算两个数的乘积
   public static int multipy(int a, int b){
   	int count = a * b;
   	
   	return count;
   	
   }

   //打印语句功能
   public static void print(){
   	System.out.println("哇,有美女....");
   }

   //清理系统垃圾功能
   public static void clear(){
   	for (int i = 0; i < 1000; i++) {
   		System.out.println("系统清理中....");
   	}
   }
   ```

7. **测试题**

   * 定义一个获取整数绝对值的方法, 并调用
   * 定义一个计算一定范围内整数和的方法, 并调用

8. **参数传递**

   * 调用方法时,传递一个实参,就相当于将这个实参赋值给形参

## 二. 方法的重载(overloading)

1. **定义**
   * 一个类里面出现多个方法名相同 , 参数列表不同的多个方法 , 我们叫这种现象为方法重载
   * 方法重载是为了提高方法名的使用率 , 毕竟意思相同的单词就那么几个 , 而且 我们的方法功能也类似 , 这种情况下如果使用不用的方法名 , 很可能造成意义混 乱 , 所以就出现了方法重载
   * 在我们的程序中绝对不允许出现两个一模一样的方法, 如果我们能想办法让jvm区别每个方法,那么这个方法就可以使用

2. **参数列表**
   * 参数个数不同
   * 参数类型不同
   * 参数的顺序不同(也算是重载,但是一般开发中不用, 没有意义)

3. **案例演示**

   ```java
   public static void method(int i,double d){
   	
   	
   }
   //和第一个方法的参数个数不同
   public static void method(int i){
   }

   //和第一个方法的参数的类型不同
   public static void method(String str,float f){

   }

   //和第一个方法的参数的顺序不同
   public static void method(double d,int i){

      	
   }
   ```


4. **测试题**

   * 定义两个重载方法, 一个方法是计算两个整数的和, 一个方法是计算三个整数的和
   * 定义两个重载方法, 比较两个int型和double型是否相等

## 三. 数组

1. **数组**

   * 组就是指多个的意思 , 在之前我们的代码中使用的数据类型都是单个的 , 为了将多个相同类型的数据存储在一起 , 这时候就引出了组的概念
   * 数组是存储同一种数据类型多个元素的集合, 也可以看成是一个容器
   * 数组可以存储基本数据类型,也可以存储引用数据类型
   * 数组是java中的唯一底层容器

2. **数组的初始化**

   * 就是为数组开辟连续的内存空间, 并为每个数组元素赋值

   * 静态初始化

     * 指定内容,数组的长度由jvm自动判断
     * 数据类型[] 数组名 = new 数据类型[ ]{元素,元素,元素,元素,元素}
     * 数据类型[] 数组名 = {元素,元素,元素,元素,元素}

   * 动态初始化

     * 指定数组的长度, 数组中的元素由jvm给出默认值
     * 数组类型[] 数组名 = new 数据类型[数组长度]

     ```java
     public static void main(String[] args) {
      	//静态初始化
      	int[] arr = {5,6,7,2,1};
      	
      	//动态初始化
      	int[] arr2 = new int[5];
     }
     ```


3. **注意事项**

   * 数组的长度在创建的时候就固定了, 中途无法被改变
   * 数组是靠角标定位元素,角标值从0开始
   * 数组属于引用数据类型
   * 数组中元素必须是同一种数据类型

4. **数组的操作**

   * 使用数组的角标对数组进行操作,我们可以将数组的一个角标位看作是一个变量
   * 获取数组的某个角标位  : arr[角标值]
     * 获取到数组中的某个角标之后, 就可以获取值和赋值了
   * 获取数组的长度(元素的个数) : arr.length

   ```java
   public static void main(String[] args) {
   	
   	int[] arr = new int[5];
   	//获取数组的0角标位
   	int i = arr[0];
   	//给数组的角标位赋值
   	arr[0] = 4;
   	
   }
   ```

5. **数组默认值**

   * 整数型 : byte short int long 默认初始化值都是0
   * 浮点型 : float double 默认初始化值都是0.0
   * 布尔型 : boolean 默认初始化值是false
   * 字符型 : char 默认初始化值是 '\u0000' 十六进制的
   * 引用数据类型 :  所有引用数据类型的初始化值都是null

   ```java
   public static void main(String[] args) {
   	//整数型 默认值是0
   	int[] is = new int[2];
   	System.out.println(is[0]);
   	//字符型 默认是值十六进制的 '\u0000'
   	char[] chs = new char[2];
   	System.out.println(chs[0]);
   	//浮点型 默认值是0.0
   	double[] ds = new double[2];
   	System.out.println(ds[0]);
   	//布尔型 默认值是false
   	boolean[] bs = new boolean[2];
   	System.out.println(bs[0]);
   	//引用数据类型默认值是null
   	String[] strs = new String[2];
   	System.out.println(strs[0]);
   	
   }
   ```

## 四. 内存图

1. **java中内存分配**
   * 栈 : 存储局部变量
   * 堆 : 存储new出来的数组或对象
   * 方法区 : 面向对象部分讲解
   * 本地方法区 : 和系统相关的方法
2. **数组动静态初始化步骤**
   * 动态初始化
     * 开辟连续的内存空间
     * 分配角标
     * 赋上默认值
   * 动态初始化
     * 开辟连续的内存空间0
     * 分配角标
     * 赋值指定的值
3. **多个变量引用同一个数组**
   * 在栈中创建多个变量
   * 多个变量执行堆中的同一个数组对象

## 五. 数组常见的问题

1. ArrayIndexOutOfBoundsException

   * 数组角标越界异常
   * 访问了不存在的角标

2. NullPointerException

   * 空指针异常
   * 栈中的数组变量没有指向堆内存中的数组实体

3. **演示**

   ```java
   public static void main(String[] args) {
   	
   	int[] arr = new int[2];
   	//会出现数组角标越界异常
   	int i = arr[2];
   	
   	arr = null;
   	//会出现空指针异常
   	i = arr[0];
   }
   ```


## 六. 数组的基本操作

1. **遍历数组**

   * 循环查看数组中每一个元素

     ```java
     public static void print(int[] arr){
     	for (int i = 0; i < arr.length; i++) {
     		System.out.println(arr[i]+" ");
     	}
     }
     ```

2. **获取数组中的最大值**

   * 遍历数组, 查找最大的值, 注意, 这个最大值一定是数组中的,所以我们不能随便给最大值变量赋一个默认值

     ```java
     public static int getMax(int[] arr){
     	//定义存储最大值的变量
     	int max = arr[0];
     	for (int i = 1; i < arr.length; i++) {
     		if(arr[i] > max){
     			max = arr[i];
     		}
     	}
     	return max;
     }
     ```

3. **反转数组**

   * 将数组中的元素按照排列顺序反转, 例如角标0和最后一个角标位上的元素交换

     ```java
     public static void reverse(int[] arr){
     	//数组中的元素前后交换, 遍历的次数只能是数组长度的一半
     	for (int i = 0; i < arr.length/2; i++) {
     		int temp = arr[i];
     		arr[i] = arr[arr.length-i-1];
     		arr[arr.length-i-1] = temp;
     	}
     }
     ```

4. **查找数组中某个值第一次出现的位置**

   * 对比数组中每个元素,知道匹配成功,返回当前的角标,如果没有查找到, 返回一个负数

     ```java
     public static int indexOf(int[] arr,int value){
     	//数组中的元素前后交换, 遍历的次数只能是数组长度的一半
     	for (int i = 0; i < arr.length; i++) {
     		if (arr[i]==value) {
     			return i;
     		}
     	}
     	return -1;
     }
     ```

## 七. 二分查找

1. **定义**

   * 使用折半的形式, 一次性剔除一般的无效元素, 提高了查找的效率
   * 使用二分查找的数组必须是有序的

2. **演示**

   ```java
   public static int binSearch(int[] arr, int value){
   	//定义有效元素开始的角标
   	int start = 0;
   	//定义有效元素结束的角标
   	int end = arr.length-1;
   	//定义中间的比较值
   	int mid ;
   	//当有效范围的开始角标已经大于结束角标了,说明已经没有有效元素了
   	while(start>end){
   		//计算中间的角标
   		mid = (end+start)/2;
   		if(arr[mid]==value){
   			return mid;
   		}else if(arr[mid]>value){
   			//如果中间角标位上的值大于要查找的值,
   			//说明中间值后面的数都不可能匹配上了
   			end = mid - 1;
   		}else if(arr[mid]<value){
   			//如果中间角标位上的值小于要查找的值,
   			//说明中间值前面的数都不可能匹配上了
   			start = mid + 1;
   		}
   	}
   	//没有找到的话返回-1
   	return -1;
   }
   ```

## 八. 冒泡排序

1. **定义**

   * 相邻的两个值比较, 然后交换位置, 每次循环都会将有效元素中最大的或最小的移动到有效位的最后
   * 经过多次循环之后,就可以派出一个有序的数组

2. **演示**

   ```java
   public static void bubbleSort(int[] arr){
   	//外循环控制整体的循环次数,每次都可以确定一个最大或最小元素
   	for (int i = 1; i < arr.length; i++) {
   		//内循环控制有效范围内相邻元素的比较
   		for (int j = 0; j < arr.length-i; j++) {
   			if(arr[j]>arr[j+1]){
   				int temp = arr[j];
   				arr[j] = arr[j+1];
   				arr[j+1] = temp;
   			}
   		}
   	}
   }
   ```

## 九. 二维数组

1. **定义**

   * 所谓的二维数组就是在数组中存放数组
   * 外层数组中存方法的是数组的引用

2. **初始化**

   * 静态初始化
     * 先指定数组中的内容, 长度由jvm自定判断
     * 数据类型[ ]\[ ] 数组名 = new 数组类型[ ]\[ ]{ {元素,元素},{元素,元素}}
     * 数据类型[ ]\[ ] 数组名 = { {元素,元素},{元素,元素}}
   * 动态初始化
     * 先指定数组的长度,jvm会给数组附上默认值
     * 数据类型[ ]\[ ] 数组名 = new 数组类型[数组的长度 ]\[数组的长度 ]

3. **演示**

   ```java
   public static void main(String[] args) {
   	int[][] arrs = {{2,3},{8,6},{7,5}};
   	
   	for (int i = 0; i < arrs.length; i++) {
   		//获取一个子数组, 变量子数组中的内容
   		for (int j = 0; j < arrs[i].length; j++) {
   			System.out.println(arrs[i][j]+" ");
   		}
   		System.out.println();
   	}
   }
   ```

## 作业

1. **第一题**

   * 定义一个方法, 求任意数的阶乘

2. **第二题**

   * 键盘录入5个学生的年龄, 按照从大到小对年龄进行排序

3. **第三题**

   * 键盘录入多个学生的年龄, 查找年龄为15的学生所在的位置

4. **第四题**

   * 公司年销售额求和
   * 某公司按照季度和月份统计的数据如下：单位(万元)
     * 第一季度：22,66,44
     * 第二季度：77,33,88
     * 第三季度：25,45,65
     * 第四季度：11,66,99
   * 数据额数据要求从键盘录入(扩展)

5. **扩展题**

   * 查阅资料, 思考新的数组排序方法

6. **扩展题**

   在歌唱比赛中,共有10位评委进行打分,在计算歌手得分时,去掉一个最高分,去掉一个最低分, 然后剩余的8位评委的分数进行平均,就是该选手的最终得分.输入每个评委的评分,求某选手的得分

   ​