## 一. char数据类型

1. **编码表**
   * 计算机语言将我们平时用到的字符都存放到一个表中，对应着数字
2. **char是否可以存储一个中文?**
   * 可以, 因为java使用的是Unicode编码,Unicode编码中的每个字符占用两个字节,中文也是两个字节

## 二. 算术运算符

1. **定义**

   * 就是对常量和变量进行操作的符号

2. **分类**

   * ＋ ：在java种有三种作用，正数，加法运算，字符串连接
   * － ：表示数值相减
   * ＊ ：表示数值相乘
   * ／ ：表示数值相除
   * ％ ：表示取余数 结果的正负由左边的数值决定
   * ＋＋ ：自增　对原来的数据进行＋１
   * －－：自减　对原来的数据进行－１

3. **演示**

   ```java
   public static void main(String[] args) {
   	
   	int a = 1;
   	int b = 2;
   	
   	//加
   	System.out.println(a+b);
   	//减
   	System.out.println(a-b);
   	//乘
   	System.out.println(a*b);
   	//除
   	System.out.println(a/b);
   	//摩以
   	System.out.println(a%2);
   	//自增
   	System.out.println(a++);
   	//自减
   	System.out.println(a--);
   }
   ```

4. **注意事项**

   * ++i表示先运算i自身,然后再赋值, i++表示先运算别人, 再运算自身
   * 在运算中, 我们必须将i++或者++i当作是一个整体来看,切莫和i本身混为一谈


   * 很多书籍和视频中都对i++和++i做了详细的描述, 说道i++执行四步,++i执行三步. 但是在java中没有这样的说法, 基本看不出效果. 编译器自身肯定会做优化的

5. **测试题**

   * 求 a, b, c最后的值

     ```java
     public static void main(String[] args) {
     	int a = 10;
     	int b = 10;
     	int c = 10;
     	
     	a = b++; a = 10 b = 11
     	c = --a; c = 9 a = 9 b = 11
     	b = a--; b = 9 a = 8 c = 9
     	System.out.println(a);
     	System.out.println(b);
     	System.out.println(c);
     }
     ```

   * 预测结果

     ```java
     public static void main(String[] args) {
     	int a = 1;
     	a = a++;
     	System.out.println(a);
     	
     	int b = a++ * ++a;
     	System.out.println(b);
     }
     ```

## 三. 赋值运算符

1. **定义**

   * 将数值传递给一个变量(将右边的值传递给左边)

2. **分类**

   * = : 将值传递给左边
   * += : 将左右两遍的值相加,结果再传递给左边
   * -= : 将左右两遍的值相减,结果再传递给左边
   * *= : 将左右两遍的值相乘,结果再传递给左边
   * /= : 将左右两遍的值相除,结果再传递给左边
   * %= : 将左右两遍的值相摩,结果再传递给左边

3. **演示**

   ```java
   public static void main(String[] args) {
   	int a = 10;
   	System.out.println(a);
   	//加等于
   	a += 5;
   	System.out.println(a);
   	//减等于
   	a-=6;
   	System.out.println(a);
   	//乘等于
   	a*=10;
   	System.out.println(a);
   	//除等于
   	a/=5;
   	System.out.println(a);
   	//摩等于
   	a%=2;
   	System.out.println(a);
   }
   ```

4. 测试题

   * 判断以下程序是否成立

     ```java
     public static void main(String[] args) {
     	int a ;
     	
     	a += 10;
     	
     	System.out.println(a);
     }
     ```

## 四. 关系运算符

1. **定义**

   * 一般我们也称之为判断运算符, 就是用来判断运算符两边的值的关系是否成立,结果只能是boolean

2. **分类**

   * == : 判断两边是否相等
   * != : 判断两遍是否不相等
   * \> :  判断左边是否大于右边
   * \>= : 判断左边是否大于等于右边
   * \< : 判断左边是否小于右边
   * \<= : 判断左边是否小于等于右边
   * instanceof : 判断两遍的类型是否相等

3. **演示**

   ```java
   public static void main(String[] args) {
   	
   	System.out.println(1==1);
   	
   	System.out.println(1!=1);
   	
   	System.out.println(1>1);
   	
   	System.out.println(1>=1);
   	
   	System.out.println(1<1);
   	
   	System.out.println(1<=1);

   }
   ```

4. **测试题**

   * 预测结果

     ```java
     public static void main(String[] args) {
     	
     	int a = 10;
     	int b = 20;
     	
     	boolean flg = a+b >a;
     	
     	System.out.println(flg);

     }
     ```

## 五. 逻辑运算符

1. **定义**
   * 逻辑运算符关联两个boolean结果, 结果还是一个boolean值

2. **分类**
   * & :  同时 true & true = true  true & false = flase
   * | :  或　true| true = true   true | false = true    false | false = false
   * ^ :  异或(相同为假不同为真)  true ^ true = false   false ^ false = false  rue ^ false = true
   * ! :  非  !true  = false   !false = true
   * && :  同时, 短路与, 两遍只要有一边的值为fasle , 虚拟机就不会再查看另外一边了
   * || :  或, 短路或, 两边只要有一遍的值为true, 虚拟机就不会再查看另外一边了

3. **演示**

   ```java
   public static void main(String[] args) {
   	
   	boolean b ;
   	
   	//& 同时
   	b = true&true;
   	System.out.println(b);
   	
   	b = true&false;
   	System.out.println(b);
   	
   	// | 或者
   	b = true | false;
   	System.out.println(b);
   	
   	b = false | false;
   	System.out.println(b);
   	
   	// ^ 异或, 相同为假 不同为真
   	b = true ^ true;
   	System.out.println(b);
   	
   	b = true ^ false;
   	System.out.println(b);
   	
   	// ! 非 非真即假,非假即真
   	b = !true;
   	System.out.println(b);
   	
   	b = !false;
   	System.out.println(b);
   	
   	// && 同时  如果前边是false, 后面就不再验证
   	b = false && true;
   	System.out.println(b);
   	
   	// || 或者	如果前边是true ,后面就不再验证了
   	b = true || false;
   	System.out.println(b);
   }
   ```

4. **注释事项**

   * 短路与和短路或运算符前后是否都执行, 主要看第一个条件

## 六. 位运算符

1. **定义**

   * 对数值进行二进制的位运算
   * 在位运算中 0 为假, 1为真

2. **分类**

   * & : 有0则为0
   * | : 有1则为1
   * ^ : 相同为0 , 不同为1 
   * ~ :  按位取反
   * \>> : 有符号右移
   * << : 有符号左移
   * \>>> : 无符号右移

3. **演示**

   ```java
   public static void main(String[] args) {
   		
   	int a = 10; //二进制表现为 1010
   	int b = 5;  //二进制表现为 0101
   	
   	System.out.println(a&b); 
   	
   	System.out.println(a|b);
   	
   	System.out.println(a^b);
   	
   	System.out.println(~a);
   	
   	System.out.println(a>>1);//右移一位 相当于除以2
   	
   	System.out.println(a<<1);//左移一位,相当于乘以2
   	
   	System.out.println(a>>>1);//无符号位移,缺失的首位补0
   	
   }
   ```

4. **注意事项**

   * 一个数异或同一个数两次,结果还是本身

5. **测试题**

   * 不借助第三个变量的前提下交换两个整数变量的值

## 七. 三元运算符

1. **格式**

   * boolean ? 结果1 : 结果2;
   * boolean为true,返回结果1,否则返回结果2

2. **演示**

   * 获取两个数中最大的值

     ```java
     public static void main(String[] args) {
     	int a = 10;
     	int b = 20;
     	//如果a大于b的话,结果为真,就返回a
     	int max = a > b ? a : b;	
     	System.out.println(max);
     }
     ```

## 八. 从键盘获取数据

1. **步骤**

   * 导入 java.util.Scanner;
   * 创建Scanner对象 Scanner sc = new Scanner(System.in);
   * 调用nextInt()方法获取一个整数 sc.nextInt();

2. **演示**

   ```java
   //导入类
   import java.util.Scanner;

   public class TestDemo {
   	
   	public static void main(String[] args) {
   		//创建键盘录入对象,打开键盘通道
   		Scanner sc = new Scanner(System.in);
   		//调用方法获取一个整数
   		int i = sc.nextInt();
   		System.out.println(i);
   		//关闭键盘通道
   		sc.close();
   	}
   }
   ```

## 九. 控制语句

1. **定义**
   - 一个程序,想要更加健壮, 就必须能够应对各种各样的状况, 根据实际情况来判定直接结果
   - 所以, 对于程序也应该是根据不同的情况来执行不同的顺序和语句
   - 控制语句就可以控制流程的走向和顺序
2. **分类**
   - 顺序结构
   - 选择结构
   - 循环结构

## 十. 顺序结构

1. 定义

   - 按照生活中的习惯, 从上往下,依次执行

2. 演示

   ```java
   public static void main(String[] args) {
   	//程序会从上往下依次执行
   	System.out.println("第一句话");
   	
   	System.out.println("第二句话");
   	
   	System.out.println("第三句话");
   		
   }
   ```

## 十一. 选择结构

1. **定义**
   - 可以控制部分语句执行, 执行或跳过一部分语句
2. **分类**
   - if 语句
   - switch语句

## 十二. if 语句格式一

1. **格式**

   ```java
   if(boolean){
   	//执行语句
   }
   ```

2. **执行流程**

   - 先计算if关键字后面的表达式, 看其返回值是true还是false
   - 如果是true ,就执行后面大括号中的代码
   - 如果是false, 就不执行

3. **演示**

   ```java
   public static void main(String[] args) {
   	
   	int a = 1;
   	
   	if(a>0){
   		System.out.println("语句体执行了");
   	}
   	
   }
   ```

4. **注意事项**

   - if 后面的小括号里面无论写什么, 结果都必须是boolean值
   - if 语句控制的语句体如果是一条语句,大括号可以省略, 如果是多条语句, 就不能省略,建议永远不要省略
   - 一般来说, 有左大括号就没有分号, 有分号,就没有左大括号

5. **测试题**

   - 只有年龄超过18岁的学生才能玩游戏, 现在编一个程序,来判断一个学生是否可以玩游戏

## 十三. if 语句格式二

1. **格式**

   ```java
   if(boolean){
   	//语句体1
   }else{
   	//语句体2
   }
   ```

2. **执行流程**

   - 首先计算if后面小括号内的表达式的值, 看其返回值是true还是false
   - 如果是true , 就执行语句体1
   - 如果是false, 就执行语句体2

3. **案例演示**

   ```java
   public static void main(String[] args) {
   	
   	int i = 1;
   	if(i>=18){
   		System.out.println("终于可以玩游戏了");
   	}else{
   		System.out.println("哎... 再等等吧");
   	}
   	
   }
   ```

4. **注意事项**

   - else 后面是没有表达式的, 只有if后面有
   - 如果语句体只有一句话, 可以省略大括号,建议不要省略
   - 三元运算符就是这种格式的简写形式,三元运算符可以实现的,这种格式都可以,反之不行

5. **测试题**

   - 妻子嘱咐程序猿丈夫回家的时候买10苹果, 如果碰到买西瓜的买一个,编程模拟场景

## 十四. if 语句格式三

1. **格式**

   ```java
   if(boolean){
   	//语句体1
   }else if(boolean){
   	//语句体2
   }else{
   	//语句体3
   } 
   ```

2. **执行流程**

   - 首先计算if 后面括号内的表达式, 看其返回值结果
   - 如果是true就执行语句体1, if语句结束
   - 如果是false , 就执行下一个else if后面括号中的表达式,看其结果
   - 如果是true ,就执行语句体2 
   - 如果是false , 就接着判断下一个else if后面表达式的结果
   - 以此类推, 直到最后执行else语句结束
   - 如果中途有一个if或者else if 后的括号判断结果是true ,则之后的代码都不再执行

3. **注意事项**

   - 最后一个else可以省略, 但建议不要省略, 可以对有效值范围外的错误值进行提示

4. **演示**

   ```java
   public static void main(String[] args) {
   	
   	int i = 10;
   	if(i>18){
   		System.out.println("吃鸡");
   	}else if(i>10){
   		System.out.println("LOL");
   	}else if(i>3){
   		System.out.println("王者农药");
   	}else{
   		System.out.println("泡妞");
   	}
   	
   }
   ```

5. **测试题**

   - 从键盘录入一个学生的成绩, 判断其成绩的等级

## 作业

1. **第一题**

   * 使用键盘录入三个整数, 求出三个整数中最大的那个并打印

2. **第二题**

   - 饭店里面有五道菜, 黄花鱼 200块, 烤鸭 100块, 红烧肉 60块, 小炒肉 40块, 白水豆腐 10块
   - 一个客人进了饭店, 根据身上的钱来决定最好能吃哪道菜 , 编程模拟

3. **第三题**

   * 判断flg的结果

   ```java
   public static void main(String[] args) {
   	boolean flg = false | (true & (false^true));
   }
   ```

4. **扩展题**

   * 求出 j 的结果 , 写出运算步骤

   ```java
   public static void main(String[] args) {
   	int i=3,j;   
   	
   	j=(i++)+(i++)+(++i);
   	
   	System.out.println(j);
   }
   ```

5. **扩展题**

   * 思考, java中域嵌套的情况下, 变量的重名问题? 哪些是可以使用相同变量名的,哪些是不能使用相同变量名的?