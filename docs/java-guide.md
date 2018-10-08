## 命名风格

1. 【强制】代码中的命名均不能以<strong>下划线或美元符号</strong>开始，也不能以<strong>下划线或美元符号</strong>结束。
  <br><span style="color:red">反例</span>：`_name / __name / $name / name_ / name$ / name__`
2. 【强制】代码中的命名严禁使用拼音与英文混合的方式，更不允许直接使用中文的方式。 
  <br><span style="color:orange">说明</span>：正确的英文拼写和语法可以让阅读者易于理解，避免歧义。注意，即使纯拼音命名方式也要避免采用。 
  <br><span style="color:green">正例</span>：alibaba / taobao / youku / hangzhou 等国际通用的名称，可视同英文。 
  <br><span style="color:red">反例</span>：DaZhePromotion [打折] / getPingfenByName() [评分] / int 某变量 = 3 
3. 【强制】类名使用`UpperCamelCase`风格，但以下情形例外：DO / BO / DTO / VO / AO / PO等。 
 <br><span style="color:green">正例</span>：MarcoPolo / UserDO / XmlService / TcpUdpDeal / TaPromotion 
 <br><span style="color:red">反例</span>：macroPolo / UserDo / XMLService / TCPUDPDeal / TAPromotion 
4. 【强制】方法名、参数名、成员变量、局部变量都统一使用`lowerCamelCase`风格，必须遵从驼峰形式。 
<br><span style="color:green">正例</span>： localValue / getHttpMessage() / inputUserId 
5. 【强制】常量命名全部大写，单词间用下划线隔开，力求语义表达完整清楚，不要嫌名字长。 
<br><span style="color:green">正例</span>：MAX_STOCK_COUNT 
<br><span style="color:red">反例</span>：MAX_COUNT 
6. 【强制】抽象类命名使用Abstract或Base开头；异常类命名使用Exception结尾；测试类命名以它要测试的类名开始，以Test结尾。 
7. 【强制】类型与中括号紧挨相连来定义数组。 
 <br><span style="color:green">正例</span>：定义整形数组<code>int[] arrayDemo;</code> 
 <br><span style="color:red">反例</span>：在main参数中，使用<code>String args[]</code>来定义。 
8. 【强制】POJO类中布尔类型的变量，都不要加is前缀，否则部分框架解析会引起序列化错误。 
 <br><span style="color:red">反例</span>：定义为基本数据类型<code>Boolean isDeleted；</code>的属性，它的方法也是<code>isDeleted()</code>，RPC框架在反向解析的时候，“误以为”对应的属性名称是deleted，导致属性获取不到，进而抛出异常。
9. 【强制】包名统一使用小写，点分隔符之间有且仅有一个自然语义的英语单词。包名统一使用单数形式，但是类名如果有复数含义，类名可以使用复数形式。 
 <br><span style="color:green">正例</span>：应用工具类包名为com.alibaba.ai.util、类名为MessageUtils（此规则参考spring的框架结构） 
10. 【强制】杜绝完全不规范的缩写，避免望文不知义。 
 <br><span style="color:red">反例</span>：AbstractClass“缩写”命名成AbsClass；condition“缩写”命名成 condi，此类随意缩写严重降低了代码的可阅读性。 
11. 【推荐】为了达到代码自解释的目标，任何自定义编程元素在命名时，使用尽量完整的单词组合来表达其意。 
<br><span style="color:green">正例</span>：从远程仓库拉取代码的类命名为PullCodeFromRemoteRepository。 
<br><span style="color:red">反例</span>：变量int a; 的随意命名方式。 
12. 【推荐】如果模块、接口、类、方法使用了设计模式，在命名时体现出具体模式。 
<br><span style="color:orange">说明</span>：将设计模式体现在名字中，有利于阅读者快速理解架构设计理念。 
<br><span style="color:green">正例</span>：
```
public class OrderFactory;
public class LoginProxy;
public class ResourceObserver; 
```
13. 【推荐】接口类中的方法和属性不要加任何修饰符号（public 也不要加），保持代码的简洁性，并加上有效的Javadoc注释。尽量不要在接口里定义变量，如果一定要定义变量，肯定是与接口方法相关，并且是整个应用的基础常量。 
<br><span style="color:green">正例</span>：接口方法签名void f(); 接口基础常量String COMPANY = "alibaba"; 
<br><span style="color:red">反例</span>：接口方法定义public abstract void f(); 
<br><span style="color:orange">说明</span>：JDK8中接口允许有默认实现，那么这个default方法，是对所有实现类都有价值的默认实现。 
14. 接口和实现类的命名有两套规则：  
   1）【强制】对于Service和DAO类，基于SOA的理念，暴露出来的服务一定是接口，内部的实现类用Impl的后缀与接口区别。 
   <br><span style="color:green">正例</span>：CacheServiceImpl实现CacheService接口。<br>
   2） 【推荐】 如果是形容能力的接口名称，取对应的形容词为接口名（通常是–able的形式）。
   <br><span style="color:green">正例</span>：AbstractTranslator实现 Translatable。 
15. 【参考】枚举类名建议带上Enum后缀，枚举成员名称需要全大写，单词间用下划线隔开。 
<br><span style="color:orange">说明</span>：枚举其实就是特殊的常量类，且构造方法被默认强制是私有。 
<br><span style="color:green">正例</span>：枚举名字为ProcessStatusEnum的成员名称：SUCCESS / UNKNOWN_REASON。 
16. 【参考】各层命名规约：  
  A) Service/DAO层方法命名规约<br>
   1） 获取单个对象的方法用get作前缀。
   <br>2） 获取多个对象的方法用list作前缀。
   <br>3） 获取统计值的方法用count作前缀。    
   4） 插入的方法用save/insert作前缀。    
   5） 删除的方法用remove/delete作前缀。    
   6） 修改的方法用update作前缀。 
  <br>B) 领域模型命名规约 <br>
   1） 数据对象：xxxDO，xxx即为数据表名。    
   2） 数据传输对象：xxxDTO，xxx为业务领域相关的名称。    
   3） 展示对象：xxxVO，xxx一般为网页名称。    
   4） POJO是DO/DTO/BO/VO的统称，禁止命名成xxxPOJO。 

## 常量定义

1. 【强制】不允许任何魔法值（即未经预先定义的常量）直接出现在代码中。
<br><span style="color:red">反例</span>：
```
String key = "Id#taobao_" + tradeId;       
cache.put(key, value); 
```
2. 【强制】long或者Long初始赋值时，使用大写的L，不能是小写的l，小写容易跟数字1混淆，造成误解。 
<br><span style="color:orange">说明</span>：<pre>Long a = 2l;</pre> 写的是数字的`21`，还是Long型的`2`? 
3. 【推荐】不要使用一个常量类维护所有常量，按常量功能进行归类，分开维护。 
<br><span style="color:orange">说明</span>：大而全的常量类，非得使用查找功能才能定位到修改的常量，不利于理解和维护。 
<br><span style="color:green">正例</span>：缓存相关常量放在类CacheConsts下；系统配置相关常量放在类ConfigConsts下。 
4. 【推荐】常量的复用层次有五层：跨应用共享常量、应用内共享常量、子工程内共享常量、包内共享常量、类内共享常量。  
1） 跨应用共享常量：放置在二方库中，通常是client.jar中的constant目录下。
2） 应用内共享常量：放置在一方库中，通常是子模块中的constant目录下。
<br><span style="color:red">反例</span>：易懂变量也要统一定义成应用内共享常量，两位攻城师在两个类中分别定义了表示“是”的变量：
```
    类A中：public static final String YES = "yes";
    类B中：public static final String YES = "y";
    A.YES.equals(B.YES) 预期是true，但实际返回为false，导致线上问题。
```
3） 子工程内部共享常量：即在当前子工程的constant目录下。  
4） 包内共享常量：即在当前包下单独的constant目录下。  
5） 类内共享常量：直接在类内部private static final定义。 
5. 【推荐】如果变量值仅在一个固定范围内变化用enum类型来定义。 说明：如果存在名称之外的延伸属性使用enum类型，下面正例中的数字就是延伸信息，表示一年中的第几个季节。 
 <br><span style="color:green">正例</span>： 
```
  public enum SeasonEnum {   
          SPRING(1), SUMMER(2), AUTUMN(3), WINTER(4);
          int seq; 
          SeasonEnum(int seq){         
              this.seq = seq;     
          } 
  } 
```

## 代码格式
1. 【强制】大括号的使用约定。如果是大括号内为空，则简洁地写成`{}`即可，不需要换行；如果是非空代码块则：
<br>1） 左大括号前不换行。
<br>2） 左大括号后换行。
<br>3） 右大括号前换行。
<br>4） 右大括号后还有else等代码则不换行；表示终止的右大括号后必须换行。 
2. 【强制】 左小括号和字符之间不出现空格；同样，右小括号和字符之间也不出现空格。详见第5条下方正例提示。
<br><span style="color:red">反例</span>：
```
if (空格a == b空格)
```
3. 【强制】if/for/while/switch/do等保留字与括号之间都必须加空格。 
4. 【强制】任何二目、三目运算符的左右两边都需要加一个空格。 
   <br><span style="color:orange">说明</span>：运算符包括赋值运算符=、逻辑运算符&&、加减乘除符号等。
5. 【强制】采用4个空格缩进，禁止使用tab字符。 
   <br><span style="color:orange">说明</span>：
    如果使用tab缩进，必须设置1个tab为4个空格。IDEA设置tab为4个空格时，请勿勾选`Use tab character`；而在eclipse中，必须勾选`insert spaces for tabs`。 
   <br><span style="color:green">正例</span>： （涉及1-5点）

          public static void main(String[] args) {
              // 缩进4个空格
              String say = "hello";
              // 运算符的左右必须有一个空格
              int flag = 0;
              // 关键词if与括号之间必须有一个空格，括号内的f与左括号，0与右括号不需要空格
              if (flag == 0) {
                  System.out.println(say);
              }
              // 左大括号前加空格且不换行；左大括号后换行
              if (flag == 1) {
                  System.out.println("world");
                  // 右大括号前换行，右大括号后有else，不用换行
              } else {
                  System.out.println("ok");
                  // 在右大括号后直接结束，则必须换行
              }
          }

6. 【强制】注释的双斜线与注释内容之间有且仅有一个空格。 
 <br><span style="color:green">正例</span>：
```
// 这是示例注释，请注意在双斜线之后有一个空格  
String ygb = new String(); 
```
7. 【强制】单行字符数限制不超过120个，超出需要换行，换行时遵循如下原则：
<br>1）第二行相对第一行缩进4个空格，从第三行开始，不再继续缩进，参考示例。
<br>2）运算符与下文一起换行。
<br>3）方法调用的点符号与下文一起换行。
<br>4） 方法调用时，多个参数，需要换行时，在逗号后进行。
<br>5） 在括号前不要换行，见反例。
<br><span style="color:green">正例</span>：
```
StringBuffer sb = new StringBuffer();
     // 超过120个字符的情况下，换行缩进4个空格，点号和方法名称一起换行
    sb.append("zi").append("xin")...
                   .append("huang")...
                   .append("huang")...
                   .append("huang");
```
<br><span style="color:red">反例</span>：
```
StringBuffer sb = new StringBuffer();  
// 超过120个字符的情况下，不要在括号前换行  
sb.append("zi").append("xin")...append      
("huang");    
// 参数很多的方法调用可能超过120个字符，不要在逗号前换行  
method(args1, args2, args3, ... 
, argsX); 
```
8. 【强制】方法参数在定义和传入时，多个参数逗号后边必须加空格。 
<br><span style="color:green">正例</span>：下例中实参的"a",后边必须要有一个空格。 
```
method("a", "b", "c"); 
```
9. 【强制】IDE的text file encoding设置为UTF-8; IDE中文件的换行符使用Unix格式，不要使用Windows格式。 
10. 【推荐】没有必要增加若干空格来使某一行的字符与上一行对应位置的字符对齐。 
<br><span style="color:green">正例</span>： 
```
int a = 3;  
long b = 4L;  
float c = 5F;  
StringBuffer sb = new StringBuffer();
```
<span style="color:orange">说明</span>：增加sb这个变量，如果需要对齐，则给a、b、c都要增加几个空格，在变量比较多的情况下，是非常累赘的事情。 
11. 【推荐】不同逻辑、不同语义、不同业务的代码之间插入一个空行分隔开来以提升可读性。 
<br><span style="color:orange">说明</span>：没有必要插入**多个空行**进行隔开。 

## OOP规约 

1. 【强制】避免通过一个类的对象引用访问此类的静态变量或静态方法，无谓增加编译器解析成本，直接用**类名**来访问即可。 
2. 【强制】所有的覆写方法，必须加@Override注解。 
<br><span style="color:orange">说明</span>：getObject()与get0bject()的问题。一个是字母的O，一个是数字的0，加@Override可以准确判断是否覆盖成功。另外，如果在抽象类中对方法签名进行修改，其实现类会马上编译报错。 
3. 【强制】相同参数类型，相同业务含义，才可以使用Java的可变参数，避免使用Object。 
<br><span style="color:orange">说明</span>：可变参数必须放置在参数列表的最后。（提倡同学们尽量不用可变参数编程） 
<br><span style="color:green">正例</span>：
```
public User getUsers(String type, Integer... ids) {...} 
```
4. 【强制】外部正在调用或者二方库依赖的接口，不允许修改方法签名，避免对接口调用方产生影响。接口过时必须加`@Deprecated`注解，并清晰地说明采用的新接口或者新服务是什么。 
5. 【强制】不能使用过时的类或方法。 
<br><span style="color:orange">说明</span>：java.net.URLDecoder 中的方法decode(String encodeStr) 这个方法已经过时，应该使用双参数decode(String source, String encode)。接口提供方既然明确是过时接口，那么有义务同时提供新的接口；作为调用方来说，有义务去考证过时方法的新实现是什么。 
6. 【强制】Object的equals方法容易抛空指针异常，应使用常量或确定有值的对象来调用equals。
<br><span style="color:green">正例</span>："test".equals(object);
<br><span style="color:red">反例</span>：object.equals("test"); 
<br><span style="color:orange">说明</span>：推荐使用java.util.Objects#equals（JDK7引入的工具类）
7. 【强制】所有的相同类型的包装类对象之间值的比较，全部使用equals方法比较。 
<br><span style="color:orange">说明</span>：对于Integer var = ?  在-128至127范围内的赋值，Integer对象是在IntegerCache.cache产生，会复用已有对象，这个区间内的Integer值可以直接使用==进行判断，但是这个区间之外的所有数据，都会在堆上产生，并不会复用已有对象，这是一个大坑，推荐使用equals方法进行判断。 
8. 关于基本数据类型与包装数据类型的使用标准如下：
<br>1） 【强制】所有的POJO类属性必须使用包装数据类型。
<br>2） 【强制】RPC方法的返回值和参数必须使用包装数据类型。
<br>3） 【推荐】所有的局部变量使用基本数据类型。
<br><span style="color:orange">说明</span>：POJO类属性没有初值是提醒使用者在需要使用时，必须自己显式地进行赋值，任何NPE问题，或者入库检查，都由使用者来保证。
<br><span style="color:green">正例</span>：数据库的查询结果可能是null，因为自动拆箱，用基本数据类型接收有NPE风险。
<br><span style="color:red">反例</span>：比如显示成交总额涨跌情况，即正负x%，x为基本数据类型，调用的RPC服务，调用不成功时，返回的是默认值，页面显示为0%，这是不合理的，应该显示成中划线。所以包装数据类型的null值，能够表示额外的信息，如：远程调用失败，异常退出。 
9. 【强制】定义DO/DTO/VO等POJO类时，不要设定任何属性**默认值**。
<br><span style="color:red">反例</span>：POJO类的gmtCreate默认值为new Date();但是这个属性在数据提取时并没有置入具体值，在更新其它字段时又附带更新了此字段，导致创建时间被修改成当前时间。 
10. 【强制】序列化类新增属性时，请不要修改serialVersionUID字段，避免反序列失败；如果完全不兼容升级，避免反序列化混乱，那么请修改serialVersionUID值。 
<br><span style="color:orange">说明</span>：注意serialVersionUID不一致会抛出序列化运行时异常。 
11. 【强制】构造方法里面禁止加入任何业务逻辑，如果有初始化逻辑，请放在init方法中。 
12. 【强制】POJO类必须写toString方法。使用IDE中的工具：source> generate toString时，如果继承了另一个POJO类，注意在前面加一下super.toString。 <br><span style="color:orange">说明</span>：在方法执行抛出异常时，可以直接调用POJO的toString()方法打印其属性值，便于排查问题。 
13. 【推荐】使用索引访问用String的split方法得到的数组时，需做最后一个分隔符后有无内容的检查，否则会有抛IndexOutOfBoundsException的风险。 
<br><span style="color:orange">说明</span>：
```
String str = "a,b,c,,";  
String[] ary = str.split(",");  
// 预期大于3，结果是3 System.out.println(ary.length);
```
14. 【推荐】当一个类有多个构造方法，或者多个同名方法，这些方法应该按顺序放置在一起，便于阅读，此条规则优先于第15条规则。 
15. 【推荐】 类内方法定义的顺序依次是：公有方法或保护方法 > 私有方法 > getter/setter方法。
<br><span style="color:orange">说明</span>：公有方法是类的调用者和维护者最关心的方法，首屏展示最好；保护方法虽然只是子类关心，也可能是“模板设计模式”下的核心方法；而私有方法外部一般不需要特别关心，是一个黑盒实现；因为承载的信息价值较低，所有Service和DAO的getter/setter方法放在类体最后。 
16. 【推荐】setter方法中，参数名称与类成员变量名称一致，this.成员名 = 参数名。在getter/setter方法中，不要增加业务逻辑，增加排查问题的难度。
<br><span style="color:red">反例</span>：
```
  public Integer getData() {      
      if (condition) {  
        return this.data + 100;  
      } else { 
        return this.data - 100; 
      }  
  }
```
17. 【推荐】循环体内，字符串的连接方式，使用StringBuilder的append方法进行扩展。
<br><span style="color:orange">说明</span>：反编译出的字节码文件显示每次循环都会new出一个StringBuilder对象，然后进行append操作，最后通过toString方法返回String对象，造成内存资源浪费。  <br><span style="color:red">反例</span>：
```
  String str = "start";
  for (int i = 0; i < 100; i++) {
      str = str + "hello";      
  }
```
18. 【推荐】final可以声明类、成员变量、方法、以及本地变量，下列情况使用final关键字：
<br>1） 不允许被继承的类，如：String类。
<br>2） 不允许修改引用的域对象，如：POJO类的域变量。
<br>3） 不允许被重写的方法，如：POJO类的setter方法。
<br>4） 不允许运行过程中重新赋值的局部变量。
<br>5） 避免上下文重复使用一个变量，使用final描述可以强制重新定义一个变量，方便更好地进行重构。 
19. 【推荐】慎用Object的clone方法来拷贝对象。 
<br><span style="color:orange">说明</span>：对象的clone方法默认是浅拷贝，若想实现深拷贝需要重写clone方法实现属性对象的拷贝。 
20. 【推荐】类成员与方法访问控制从严：
<br>1） 如果不允许外部直接通过new来创建对象，那么构造方法必须是private。
<br>2） 工具类不允许有public或default构造方法。
<br>3） 类非static成员变量并且与子类共享，必须是protected。
<br>4） 类非static成员变量并且仅在本类使用，必须是private。
<br>5） 类static成员变量如果仅在本类使用，必须是private。
<br>6） 若是static成员变量，必须考虑是否为final。
<br>7） 类成员方法只供类内部调用，必须是private。
<br>8） 类成员方法只对继承类公开，那么限制为protected。 
<br><span style="color:orange">说明</span>：任何类、方法、参数、变量，严控访问范围。过于宽泛的访问范围，不利于模块解耦。思考：如果是一个private的方法，想删除就删除，可是一个public的service成员方法或成员变量，删除一下，不得手心冒点汗吗？变量像自己的小孩，尽量在自己的视线内，变量作用域太大，无限制的到处跑，那么你会担心的。 