title: 开发经验总结
categories:
  - 编程
tags:
  - 思考
date: 2017-08-21 10:34:00
---
# 编程发展史


## 计算机模型

### 图灵机
所谓的图灵机就是指一个抽象的机器，它有一条无限长的纸带，纸带分成了一个一个的小方格，每个方格有不同的颜色。有一个机器头在纸带上移来移去。机器头有一组内部状态，还有一些固定的程序。

在每个时刻，机器头都要从当前纸带上读入一个方格信息，然后结合自己的内部状态查找程序表，根据程序输出信息到纸带方格上，并转换自己的内部状态，然后进行移动。

图灵机就是有限状态机 加上 无限长磁带（其实就是内存的概念）的组合

### 冯·诺依曼体系结构
美籍匈牙利数学家冯·诺依曼于1946年提出存储程序原理，把程序本身当作数据来对待，程序和该程序处理的数据用同样的方式储存。

冯诺依曼结构计算机由五大部件组成，运算器、控制器、存储器、输入设备、输出设备

冯.诺依曼体系结构是现代计算机的基础，现在大多计算机仍是冯.诺依曼计算机的组织结构，只是作了一些改进而已，并没有从根本上突破冯体系结构的束缚。冯.诺依曼也因此被人们称为“计算机之父”


## 编程语言的演化

### 机器语言
机器语言是二进制机器代码编成的代码序列，用来控制计算机执行规定的操作。其特点是能直接反映计算机的硬件结构,并且用机器语言编写的程序不须作任何处理即可直接输入计算机执行。由于机器语言与机器是一对一的,不同的机器有不同的指令系统,一种机器编写的程序也无法直接搬到另一种机器上运行。一个问题如果需要在多种机器上求解,那么就必须对同一问题重复编写多个应用程序

#### 背景
先让我们穿越一下来到1880左右的美国，美国建国时在宪法里包括了这么一条：“政府每十年要进行一次人口普查“。

刚好1880年就是一个人口普查年，这次的普查数据处理还是靠人工操作。住在同一住址的人的信息被写在一张纸上，然后这些记录被集中在华盛顿进行统计。

虽然人口总数在几个月就数出来了，但像每个州有多少20岁到25岁男童鞋这类的详细的问题给出答案就是八年后的事了。

政府一看，这不行啊！下次普查就又要来了，人口肯定更多，想回答的问题也更精彩，这样下去可能十年也干不完。这也不是个事，怎么办？人口统计局于是出个告示请大家想办法呗。

这时有个叫 Herman Hollerith (赫尔曼·霍尔瑞斯，1860-1929) 的年轻人跳出来说有想法了，发明了打孔计数器。

到了20世纪初，霍尔瑞斯的公司（the Tabulating Machine Company）有了远多于他们可以服务的客户。因为他们只租不卖，所以用来生产计数器的现金流总是很紧张，最好的解决方案似乎就是合并。

于是霍尔瑞斯的公司在1911年与其他三家公司合并成为了the Computing-Tabulating-Recording Company （CTR）。而这家公司最后就成为了我们熟知的 the International Business Machines Corporation（IBM）

在霍尔瑞斯的打孔计数器后，打孔卡片用来存储数据信息和控制计算流程的功能被逐渐应用在更多的仪器中。到现代计算机被设计出来时，打孔卡片在很长一段时间内都还一直是数据和程序的载体。而数据输入和编程这些事也就是给卡片打孔，要细心耐心才行，所以最早的码农们也主要以女神为主

#### 卡片编程
卡片编程是二进制编程，有孔代表为1，无空代表为0，应该是最早的编程方式了。

### 汇编语言
由于机器语言程序的直观性差，且与人们习惯使用的数学表达式及自然语言差距太大，导致机器语言难学、难记，编写出来的程序难以调试、修改、移植和维护，极大限制了计算机的推广。

在这种情况下，用助记符号（mnemonic symbol）来表示机器指令的操作符与操作数(亦称运算符与运算对象)，用地址符号（address symbol）代替指令或操作数的地址的 ***汇编语言*** 出现了。

机器不能直接识别使用汇编语言编写的程序，还要由汇编语言编译器转换成机器指令才能运行

### 高级语言
1954年，第一个完全脱离机器硬件的高级语言——FORTRAN语言问世了。高级语言在不同的平台上会被编译成不同的机器语言，使得程序设计语言不再过度的依赖某种特定的机器或者语言环境。

1970年，一个标志着结构化程序设计时期开始的语言问世了，它就是Pascal语言。这个标致性的语言拥有严格的结构化形式、丰富且完备的数据类型，运行效率高、查错能力强。同时Pascal语言还是一种自编译语言。

而后各种高级语言，诸如C，C++，Java，C#，PHP，Javascript，Python，Ruby，Scala，Golang等都如雨后春笋一样纷纷出世，使得编程语言达到了新的高度



# 软件开发


## 开发流程
1. 需求调研分析 　　
	- 相关系统分析员和用户初步了解需求，然后列出要开发的系统的大功能模块，每个大功能模块有哪些小功能模块，对于有些需求比较明确相关的界面时，在这一步里面可以初步定义好少量的界面。 　　
	- 系统分析员深入了解和分析需求，根据自己的经验和需求用WORD或相关的工具再做出一份文档系统的功能需求文档。这次的文档会清楚例用系统大致的大功能模块，大功能模块有哪些小功能模块，并且还例出相关的界面和界面功能。 　　
	- 系统分析员和用户再次确认需求。
    
2. 概要设计 　　
	- 首先，开发者需要对软件系统进行概要设计，即系统设计。概要设计需要对软件系统的设计 进行考虑，包括系统的基本处理流程、系统的组织结构、模块划分、功能分配、接口设计、 运行设计、数据结构设计和出错处理设计等，为软件的详细设计提供基础。
    - 其次，需要对使用的技术进行选择，对软件的支撑的具体规模进行初步估计，对未来的扩展和重构进行初步考虑
    
3. 详细设计 　　
	- 在概要设计的基础上，开发者需要进行软件系统的详细设计。在详细设计中，描述实 现具体模块所涉及到的主要算法、数据结构、类的层次结构及调用关系，需要说明软件系统各个层次中的每一个程序(每个模块或子程序)的设计考虑，以便进行编码和测试。
    - 应当保证软件的需求完全分配给整个软件。详细设计应当足够详细，能够根据详细设计报告进行编码。
    
4. 编码    　　
	- 在软件编码阶段，开发者根据《软件系统详细设计报告》中对数据结构、算法分析和模块实现等方面的设计要求，开始具体的编写程序工作，分别实现各模块的功能，从而实现对目标系统的功能、性能、接口、界面等方面的要求。
    - 编码完成后要进行联合调试和初步的测试，尽可能减少错误

5. 测试
	- 对软件的基本功能进行测试，保证功能的完整性，包括黑盒测试和白盒测试
    - 对软件进行压力测试，校验软件的性能能否达到要求
    - 合理性和易用性测试，保证软件能够被很好的使用

6. 软件交付　　
	- 在软件测试证明软件达到要求后，软件开发者应向用户提交开发的目标安装程序、数据库的数据字典、《用户安装手册》、《用户使用指南》、需求报告、设计报告、测试报告等双方合同约定的产物。 　　
	- 《用户安装手册》应详细介绍安装软件对运行环境的要求、安装软件的定义和内容、在客户端、服务器端及中间件的具体安装步骤、安装后的系统配置。 　　
    - 《用户使用指南》应包括软件各项功能的使用流程、操作步骤、相应业务介绍、特殊提示和注意事项等方面的内容，在需要时还应举例说明


## [开发模式][10]
1. 瀑布模型（Waterfall Model）  
瀑布模型将软件生命周期划分为制定计划、需求分析、软件设计、程序编写、软件测试和运行维护等六个基本活动，并且规定了它们自上而下、相互衔接的固定次序，如同瀑布流水，逐级下落

2. 快速原型模型（Rapid Prototype Model）  
快速原型模型的第一步是建造一个快速原型，实现客户或未来的用户与系统的交互，用户或客户对原型进行评价，进一步细化待开发软件的需求。通过逐步调整原型使其满足客户的要求，开发人员可以确定客户的真正需求是什么；第二步则在第一步的基础上开发客户满意的软件产品

3. 迭代模型（stagewise model）（也被称作迭代增量式开发或迭代进化式开发）  
在迭代式开发方法中，整个开发工作被组织为一系列的短小的、固定长度（如3周）的小项目，被称为一系列的迭代。每一次迭代都包括了需求分析、设计、实现与测试

4. 螺旋模型（Spiral Model）
螺旋模型沿着螺线进行若干次迭代，每次都由制定计划，风险分析，工程实施，客户评估四步组成。螺旋模型由风险驱动，强调可选方案和约束条件从而支持软件的重用，有助于将软件质量作为特殊目标融入产品开发之中

5. 敏捷软件开发 (Agile development)  
敏捷开发是一种以人为核心、迭代、循序渐进的开发方法。在敏捷开发中，软件项目的构建被切分成多个子项目，各个子项目的成果都经过测试，具备集成和可运行的特征。换言之，就是把一个大项目分为多个相互联系，但也可独立运行的小项目，并分别完成，在此过程中软件一直处于可使用状态


## 研发环境
1. 开发环境（本机或线下环境）  
	开发环境是开发人员所依赖的环境，可以在本机或线下机器，每个开发人员的开发环境应该相互隔离
    
2. 联调环境（线下环境）  
	每个服务都必须有一个稳定的版本部署在联调环境，供开发和测试环境使用

3. 测试环境（线下环境）  
	测试环境是测试人员使用的环境，可以和开发环境重合，方便开发人员调试

4. 灰度环境（线下环境）  
	灰度环境是预备上线的环境，不再接受大的改动，可以将流量切换到灰度环境实现平稳上线
    
5. 生产环境（线上环境）  
	生产环境是灰度环境的完全克隆，是正式对外发布服务的环境，应该得到严格的保护
    

## [持续集成][11]（Continuous integration）

### 概念
持续集成指的是频繁地（一天多次）将代码集成到主干，它的好处主要有两个
1. 快速发现引入的错误
	每完成一点更新，就集成到主干，可以快速发现错误，定位错误也比较容易。
    
2. 防止分支大幅度偏离主干
	如果不是经常集成，主干又在不断更新，会导致以后集成的难度变大，甚至难以集成。


持续集成的目的，就是让产品可以快速迭代，同时还能保持高质量。

它的核心措施是，代码集成到主干之前，必须通过自动化测试。

只要有一个测试用例失败，就不能集成

### 流程
1. 提交（GitLab）  
	流程的第一步，是开发者向代码仓库提交代码。所有后面的步骤都始于本地代码的一次提交（commit）。

2. 测试（第一轮）（Jira）
	测试有好几种，第一轮至少要跑单元测试。
    
      - 单元测试：针对函数或模块的测试
      - 集成测试：针对产品的某个功能的测试，又称功能测试
      - 性能测试（Jmeter、Loadrunner）：通过测试工具模拟多种正常、峰值以及异常负载条件来对系统各项性能指标进行测试
      - 端对端测试：从用户界面直达数据库的全链路测试
      - 自动化测试（Selenium）：在预设条件下运行测试程序，评估运行结果
    
	可以在代码仓库对commit操作配置了钩子（hook），只要提交代码或者合并进主干，就会跑自动化测试。  

3. 构建（Jenkins）  
	通过第一轮测试，代码就可以合并进主干，就算可以交付了。  

	交付后，就先进行构建（build），再进入第二轮测试。  

	所谓构建，指的是将源码转换为可以运行的实际代码，比如安装依赖，配置各种资源（样式表、JS脚本、图片）等等。

4. 测试（第二轮）（测试报告）
	构建完成，就要进行第二轮测试。如果第一轮已经涵盖了所有测试内容，第二轮可以省略，当然，这时构建步骤也要移到第一轮测试前面。  

	第二轮是全面测试，单元测试和集成测试都会跑，有条件的话，也要做端对端测试。所有测试以自动化为主，少数无法自动化的测试用例，就要人工测。 

	需要强调的是，新版本的每一个更新点都必须测试到。如果测试的覆盖率不高，进入后面的部署阶段后，很可能会出现严重的问题。

5. 部署（Jenkins，Ansible）  
	通过了第二轮测试，当前代码就是一个可以直接部署的版本（artifact）。  

	将这个版本的所有文件打包（ tar filename.tar * ）存档，发到生产服务器。  

	将打包文件解压，再将运行路径的符号链接（symlink）指向这个目录，就可以重新启动服务了。

6. 回滚
	一旦当前版本发生问题，就要回滚到上一个版本的构建结果。
    
    最简单的做法就是修改一下符号链接（symlink），指向上一个版本的目录

### [git workflow][43]
项目应该存在两个长期分支。
```
主分支master
开发分支develop
```

- master分支用于存放对外发布的版本，任何时候在这个分支拿到的都是稳定的分布版，并且需要打tag记录
- develop分支后者用于日常开发，存放预备向外发布的版本，该分支通常是用来进行全面测试的分支


其次，项目存在三种短期分支。
```
功能分支（feature branch）
补丁分支（hotfix branch）
测试分支（test branch）
```

- feature 分支用于日常功能开发
- hotfix 分支用于bug的快速修复，验证，上线
- test 分支用于对不同的一个或多个功能测试，测试完毕后合并到develop进行总体测试


## 编程思想

### 面向过程编程
面向过程编程是一种以过程为中心的编程思想，分析出解决问题的步骤，然后用函数把这些步骤一步一步实现。面向过程编程中，数据和对数据的操作是分离的

### 面相对象编程（OOP）
面向对象编程（object oriented programing）是将事物对象化，通过对象的交互来解决问题。面向对象编程中，数据和对数据的操作是绑定在一起的

### 面向过程和面相对象的区别
面向过程侧重于对问题的分析和求解

面向对象侧重于对现实世界的建模

比如说小明吃西瓜：  
面向过程 -> eat(小明，西瓜)
面向对象 -> 小明.eat(西瓜)

### [面相对象的特点][1]
1. 封装（Encapsulation）  
封装在于隐藏实现细节，使得对代码的修改更加安全和容易

2. 继承（Inheritance）  
继承在于扩展已有的功能，可以重用已有的代码

3. 多态（Polymorphism）  
多态在于表现同一种类事物的不同表现形态

### [事物之间的关系][2]
1. 泛化（Generalization）  
是一种继承关系，表现的是一般与特殊的关系, 它指定了子类如何特例化和扩展父类的特征和行为

2. 实现（Realization）
是一种约束关系，表示的是对接口所有特征和行为的实现，是对约束的实现

3. 联系（Relation）
是一种联系关系，表现的是事物之间的交互作用

	- 关联（Association）
    	比较弱的联系
    - 依赖（Dependency）
    	比较强的联系
    - 聚合（Aggregation）
    	是整体与部分的关系，且部分可以离开整体而单独存在，弱关联
    - 组合（Composition）
    	是整体与部分的关系，但部分不能离开整体而单独存在，强依赖
    
继承和组合的区别就是（is a）和（has a）的区别

### 设计模式的6大原则
软件设计的最高宗旨就是“高內聚，低耦合”，6大原则是该宗旨的体现

1. [单一职责原则][4]  
不能有多于一个导致类变更的原因，即一个类只负责一项职责

2. [里氏替换原则][5]  
子类可以扩展父类的功能但不能随意改变父类原有的功能，父类能够出现的地方子类都能够代替

3. [依赖倒置原则][6]  
高层模块不应该依赖低层模块，二者都应该依赖其抽象。抽象不应该依赖细节，细节应该依赖抽象

4. [接口隔离原则][7]  
客户端不应该依赖它不需要的接口，一个类对另一个类的依赖应该建立在最小的接口上

5. [迪米特法则][8]  
一个对象应该对其他对象保持最少的了解，减少了不必要的依赖

6. [开闭原则][9]
一个软件实体如类、模块和函数应该对扩展开放，对修改关闭

### 面向接口编程
接口体现的是一种规范和实现分离的设计哲学，充分利用接口可以极好地降低程序各模块之间的耦合，从而提高系统的可扩展性和可维护性。基于这种原则，通常推荐“面向接口”编程，而不是面向实现类编程。



# 设计模式
设计模式（Design Pattern）是一套被反复使用、多数人知晓的、经过分类的、代码设计经验的总结。
世上最复杂的东西莫过于关系，设计模式则是对关系梳理的最佳实践。

## 模式的分类
总体来说设计模式分为三大类：

- 创建型模式（对象的构建）
	- 单例模式
    - 工厂方法模式
    - 抽象工厂模式
    - 建造者模式
    - 原型模式。

- 结构型模式（对象的表现）
	- 适配器模式
    - 装饰器模式
    - 代理模式 
    - 外观模式
    - 桥接模式 
    - 组合模式
    - 享元模式

- 行为型模式（对象的交互）
	- 策略模式
    - 模板方法模式
    - 观察者模式
    - 迭代子模式
    - 责任链模式
    - 命令模式
    - 备忘录模式
    - 状态模式
    - 访问者模式
    - 中介者模式
    - 解释器模式
   
   
## 常用的模式

### 创建型模式

#### 单例模式
单例模式，是一种常用的软件设计模式。在它的核心结构中只包含一个被称为单例的特殊类。  
通过单例模式可以保证系统中一个类只有一个实例。即一个类只有一个对象实例

##### [java实现][13]
java中的单例就是通过将构造方法设置为私有，并提供方法返回唯一的实例来实现的。

如果需要线程安全，请加双重判断锁，原因可以参考[这里][14]的评论部分

1. 懒汉式单例

  ```
  //懒汉式单例类.在第一次调用的时候实例化自己   
  public class Singleton {  
      private Singleton() {}  
      private static Singleton instance = null;  
      //静态工厂方法   
      public static Singleton getInstance() {  
           if (instance == null) {    
               instance = new Singleton();  
           }    
          return instance;  
      }  
  }  
  ```

2. 饿汉式单例

  ```
  //饿汉式单例类.在类初始化的时候已经自行实例化   
  public class Singleton {  
      private Singleton() {}  
      private static final Singleton instance = new Singleton();  
      //静态工厂方法   
      public static Singleton getInstance() {  
          return instance;  
      }  
  }  
  ```

##### [python实现][15]
1. 实现__new__方法
  ```
  class Singleton(object):  
      def __new__(cls, *args, **kwargs):  
          if not hasattr(cls, '_instance'):  
              orig = super(Singleton, cls)  
              cls._instance = orig.__new__(cls, *args, **kwargs)  
          return cls._instance  
  ```

2. 使用装饰器(decorator)
  ```
  def singleton(cls):
      instances = {}
      def _singleton(*args, **kwargs):
          if cls not in instances:
              instances[cls] = cls(*args, **kwargs)
          return instances[cls]
      return _singleton
  
  @singleton  
  class Singleton(object):
      pass
  ```

#### [工厂方法][16]
##### 简单工厂
简单工厂模式的工厂类一般是使用静态方法，通过接收的参数的不同来返回不同的对象实例，不修改代码的话，是无法扩展的。

##### 工厂方法
工厂方法是针对每一种产品（对象）提供一个工厂类。通过不同的工厂实例来创建不同的产品实例，在同一类产品中，支持扩展任意增加产品

##### 抽象工厂
抽象工厂是应对产品族概念的。增加新的产品线很容易，但是无法增加新的产品

##### [控制反转和依赖注入][17]
- IoC 不是一种技术，只是一种思想，一个重要的面向对象编程的法则，它能指导我们如何设计出松耦合、更优良的程序。  
- 有了IoC容器后，把创建和查找依赖对象的控制权交给了容器，由容器进行注入组合对象，所以对象与对象之间是 松散耦合，这样也方便测试，利于功能复用，更重要的是使得程序的整个体系结构变得非常灵活  
- [Spring框架][19]是该技术的优秀代表，Spring除了IoC，还实现了[AOP][18]的设计思想

#### [建造者模式][20]
建造者模式将一个复杂对象的构建与表示分离，使得同样的构建过程可以创建不同的表示
 
### 原型模式
用原型实例指定创建对象的种类，并通过拷贝这些原型创建新的对象。原型对象主要用于对象的复制，拥有一个克隆自己的方法，Javascript的[prototype][27]就是该模式的典型应用

### 结构型模式 

#### [适配器模式][21]
适配器模式就是将一个类的接口，转换成客户期望的另一个接口，让原本接口不兼容的类可以合作无间

#### [代理模式][22]
代理模式就是给一个对象提供一个代理，并由代理对象控制对原对象的引用

#### [外观模式][23]
外观模式可以将多个类的复杂的一切隐藏在背后，只显露出一个干净美观的外观


### 行为型模式

#### [中介者模式][24]
所谓中介者模式就是用一个中介对象来封装一系列的对象交互，中介者使各对象不需要显式地相互引用，从而使其耦合松散，而且可以独立地改变它们之间的交互


### 模式之间的区别

#### 简单工厂、工厂方法、抽象工厂（开闭原则）
- 简单工厂是面向产品的，增加产品需要修改工厂
- 工厂方法是面向工厂的，增加产品只需要增加工厂
- 抽象工厂是面向产品族的，增加产品需要修改工厂，增加产品族只需要增加工厂


#### 工厂方法和建造者模式
- 工厂方法侧重于根据客户端的需求创建并返回不同的对象
- 建造者模式侧重于用不同的导演类将一系列复杂的对象组装为一个简单的对象

#### 代理模式、外观模式、中介者模式
- 代理模式PK中介者模式
  1. 代理模式是一对一，一个代理只能代表一个对象。中介者模式则是多对多，中介者的功能多样，客户也可以多个
  2. 代理模式侧重于对被代理者的模仿和控制，所以是结构型的。中介者模式侧重于建立客户和服务者之间的联系，所以是行为型的
  3. 代理模式中客户端基本感受不到服务者的存在，而中介者模式能感受到

- 外观模式PK中介者模式
  1. 外观模式是对子系统向外提供统一的接口，中介者模式侧重于建立客户和服务者之间的联系。
  2. 外观模式所有的请求处理都委托给子系统完成，而中介者模式则是协调客户和服务者共同完成业务
  3. 外观模式协议是单向，中介者模式协议是双向。

- 外观模式PK代理模式：
  1. 代理模式中的代理角色和真实角色都继承于同一类，代理角色是对被代理角色的模仿。而外观模式是多个类的集合，对外提供一个统一的的行为，数据库的[模式/内模式映象][26]就是典型的例子。
  2. 代理角色与真实角色接口相同，功能一致，代理角色实现的是真实角色的功能。外观者模式的子系统功能不同，根据用户不同需要进行配置



# 架构设计
复杂的软件必须有清晰合理的架构，否则无法开发和维护

## web发展历史
1. 静态网页  
网站开始的时候只有静态网页，后来随着html、图像、flash技术的发展以及人们对交互的需要，出现了动态网站

2. [动态网站][28]
  - 最早的动态网站开发技术是CGI（Common Gateway Interface，公用网关接口），最常用的CGI开发语言为Perl语言，python语言的前辈，许多的语言的正则表达式都借鉴了perl语言。
  - CGI程序以独立的进程运行，运行效率也比较低。为了解决CGI低效的问题，JSP（Java Server Pages），ASP（Active Server Pages），PHP（Personal Home Pages）应运而生，目前这三种也是主流的web后端开发语言。
  - 后来为了解决在服务端进行校验的缓慢（需要与服务器进行多次地往返交互）和低效（填完了表单，结果输入无效或缺少字段），JavaScript应运而生。
  - JavaScript一开始叫LiveScript，当时java语言非常火，为了利用 Java 这个因特网时髦词汇，LiveScript变成了如今的JavaScript
  - 一开始JavaScript只作为前端的脚本语言，后来随着nodejs的发展，JavaScript已经可以横跨前后端了

3. [web开发的演变][29]
	1. Web 1.0 时代。早期的开发是没有前端的，所有的页面都是通过JSP等通过模板技术直接输出html代码。后来随着前端交互越来愈复杂，前端从后端分离了出来
    2. Web 2.0 时代。为了降低复杂度，以后端为出发点，有了 Web Server 层的架构升级，比如 Structs、Spring MVC 等，MVC的架构得到了广泛的应用
    3. Web 3.0 时代。随着网站越来越复杂以及Ajax技术的出现，前端彻底分离了出来。而今，随着nodejs和众多前端框架（jquery，angular，vue，react，bootstrap）的发展，后端与前端又开始相互渗透


## 后端架构的演进
### [mvc][30]
MVC（Model-View-Controller）是最常见的软件架构之一，业界有着广泛应用，组成如下
```
视图（View）：用户界面
控制器（Controller）：业务逻辑
模型（Model）：数据保存
```

MVC模式实现了模型和视图的分离，这带来了几个好处
1. 提高开发效率和可维护性。在开发界面显示部分时，你仅仅需要考虑的是如何布局一个好的用户界面；开发模型时，你仅仅要考虑的是业务逻辑和数据维护，这样能使开发者专注于某一方面的开发，提高开发效率。
2. 一个模型提供不同的多个视图表现形式，创建新的视图而无须重写模型。一旦模型的数据发生变化，模型将通知有关的视图，每个视图相应地刷新自己。
3. 模型可复用。因为模型是独立于视图的，所以可以把一个模型独立地移植到新的平台工作。


> 所有架构的演化都是为了解耦和性能优化

### DAL 
－ DAL（Data Access Layer）是指数据访问层（外观模式）
  － 在mvc中业务逻辑和数据访问逻辑往往耦合在model层中，这样数据访问的变化很容易影响到业务而且不容易复用。
  － 随着业务的发展，数据的访问形式很容易发生变化，比如数据库表容量达到了极限，就需要分表，分库，加路由。
  － 当很多模块都需要访问数据时，DAL的存在可以使模块不用关心数据来自哪里，同构的系统或不同构的系统，数据库还是文件又或者是网络，这样就非常容易做数据迁移和相关软件的扩展和升级
  
－DAO（Data Access Object）是指数据访问对象，是DAL的基本单元

> 所有架构的演化都是为了解耦和性能优化

### 中间件技术
中间件就是非业务的技术类组件，从广义来说任何与业务无直接关系（不与某种业务直接绑定）的组件都是中间件，包括数据库，消息队列，负载均衡等等。详情参见[这里][31]

> 所有架构的演化都是为了解耦和性能优化

### 微服务
随着业务越来越复杂，服务开始拆分成各种服务，以便更好的维护和复用，比如登陆，支付，消息推送等服务许多模块都会用到。服务进行拆分后可以很容易进行很想扩展（伸缩）

1. [RMI（Remote Method Invoke）][32]  
远程方法调用，只适用于Java。

2. [Web Service][33]  
使用xml交换信息，跨平台，整体比较复杂

3. [RESTful Api][34]  
REST全称是Representational State Transfe， REST指的是一组架构约束条件和原则。” 如果一个架构符合REST的约束条件和原则，我们就称它为[RESTful架构][35]

> 所有架构的演化都是为了解耦和性能优化


## [消息机制（生产者，消费者）][36]
消息队列是系统中重要的中间件，主要解决应用耦合，异步消息，高并发等问题。实现高性能，高可用，可伸缩和最终一致性架构。尤其是大数据软件中，消息机制更是发挥的淋漓尽致

## [Master-Worker模型][44]
Master-Worker模式是常用的并行设计模式。它的核心思想是，系统有两个进程协议工作：Master进程和Worker进程。Master进程负责接收和分配任务，Worker进程负责处理子任务。
Master-Worker模式的好处是，它能将大任务分解成若干个小任务，并发执行，从而提高系统性能

### [Actor模型][37]
几十年的痛苦开发经历告诉我们，threads并不是获取并发性的好方法，往往会带来难以查找的bug。尤其是在python中，线程基本上是鸡肋（详情参考[这里][39]），好在python通过[协程][40]和[异步][41]解决了高并发的问题。Actor模型则通过 ***数据+行为+消息*** 的模式为我们提供了更好的高并发解决方案，Erlang和Scala语言中则默认添加了对Actor支持

> 所有架构的演化都是为了解耦和性能优化

## 基础服务
1. web前置服务  
向外提供api服务

2. 用户权限服务  
进行用户管理和权限控制，例如单点登陆，访问控制，容量控制，计费，开放第三方Api等

3. 业务逻辑服务  
各种业务相关的服务

4. 数据存取服务  
负责底层数据存取的服务

5. 消息处理服务  
消息处理中心，负责消息推送，发送邮件、短信等报警信息

6. 监控告警服务  
负责各种服务的监控和预警

7. 日志处理服务  
负责日志搜集和处理，以便排查问题和预警

8. 后台管理服务  
管理和运营服务



# 编程实践

## python项目的结构
```
├── bin
├── conf
├── res
├── script
├── src
└── test
```


## 编码实践
1. 写代码的第一步是先写整体的流程，有个大致的思路，不用在意具体的实现
2. 当有重复代码时，就要考虑到抽取一个方法出来
3. 不要使用魔鬼数字，如果用了，也要记得加注释
4. 重复使用的数字和字符串应当用常量变量，以便后续可能的修改
5. 方法里代码要分块书写，不要挤到一起，很难看，也很难阅读，最好每块都加上注释
6. 类的职责要分明，尽可能单一（单一职责原则）
7. 及时重构，以免到最后臃肿不堪，牵一发而动全身


---

# 参考
[面向对象的三大基石（封装，继承和复合，多态）][1]  
[UML常用图的几种关系的总结][2]  
[面向接口编程与面向实现编程][3]  
[单一职责原则][4]  
[里氏替换原则][5]  
[依赖倒置原则][6]  
[接口隔离原则][7]  
[迪米特法则][8]  
[开闭原则][9]  
[软件开发模式简介][10]  
[持续集成是什么][11]  
[Java开发中的23种设计模式详解][12]  
[JAVA设计模式之单例模式][13]  
[设计模式之单例模式(线程安全)][14]  
[Python单例模式终极版][15]  
[设计模式：简单工厂、工厂方法、抽象工厂之小结与区别][16]  
[谈谈对Spring IOC的理解][17]  
[Spring AOP 实现原理][18]  
[SSH(Struts,Spring,Hibernate)和SSM(SpringMVC,Spring,MyBatis)的区别][19]  
[设计模式读书笔记-----建造者模式][20]  
[设计模式读书笔记-----适配器模式][21]  
[设计模式读书笔记-----代理模式][22]  
[设计模式读书笔记-----外观模式][23]  
[设计模式读书笔记-----中介者模式][24]  
[设计模式读书笔记][25]  
[数据库三级模式与二级映像][26]  
[Javascript继承机制的设计思想][27]   
[常用的4种动态网页技术—CGI、ASP、JSP、PHP][28]  
[前端文摘：Web 开发模式演变历史和趋势][29]  
[MVC，MVP 和 MVVM 的图示][30]  
[浅析深究什么是中间件][31]  
[Java RMI详解][32]  
[Web Service学习笔记（webservice、soap、wsdl、jws详细分析)][33]  
[RESTful API 设计指南][34]  
[RESTful架构详解][35]    
[Message Queue 消息队列][36]  
[Actor模型][37]  
[高并发分布式事务解决之道-Actor模型(附Akka与Reactor比较)][38]  
[Python 的 GIL 是什么鬼，多线程性能究竟如何][39]  
[python协程与异步I/O][40]  
[Linux IO模式及 select、poll、epoll详解][41]  
[22种代码的坏味道，一句话概括][42]  
[Git 工作流程][43]  
[并行程序设计模式--Master-Worker模式][44]  
[python使用master worker管理模型开发服务端][45]  

[1]: http://blog.chinaunix.net/uid-20791902-id-291984.html\
[2]: http://blog.csdn.net/suxinpingtao51/article/details/8011335
[3]: http://blog.csdn.net/u013400743/article/details/51252003
[4]: http://blog.csdn.net/zhengzhb/article/details/7278174
[5]: http://blog.csdn.net/zhengzhb/article/details/7281833
[6]: http://blog.csdn.net/zhengzhb/article/details/7289269
[7]: http://blog.csdn.net/zhengzhb/article/details/7296921
[8]: http://blog.csdn.net/zhengzhb/article/details/7296930
[9]: http://blog.csdn.net/zhengzhb/article/details/7296944
[10]: http://www.cnblogs.com/liang--liang/p/3613815.html
[11]: http://www.ruanyifeng.com/blog/2015/09/continuous-integration.html
[12]: http://www.cnblogs.com/maowang1991/archive/2013/04/15/3023236.html
[13]: http://blog.csdn.net/jason0539/article/details/23297037/
[14]: http://www.cnblogs.com/xudong-bupt/p/3433643.html
[15]: http://blog.csdn.net/ghostfromheaven/article/details/7671914
[16]: http://zyjustin9.iteye.com/blog/2094960
[17]: http://blog.csdn.net/qq_22654611/article/details/52606960
[18]: http://blog.csdn.net/moreevan/article/details/11977115/
[19]: http://blog.csdn.net/gane_cheng/article/details/52795914
[20]: http://www.cnblogs.com/chenssy/p/3307787.html
[21]: http://blog.csdn.net/chenssy/article/details/9393827
[22]: http://blog.csdn.net/chenssy/article/details/11179815
[23]: http://blog.csdn.net/chenssy/article/details/9428553
[24]: http://blog.csdn.net/chenssy/article/details/18443883
[25]: http://blog.csdn.net/column/details/chenssy-design.html?&page=1
[26]: http://blog.csdn.net/bigpudding24/article/details/50675081
[27]: http://www.ruanyifeng.com/blog/2011/06/designing_ideas_of_inheritance_mechanism_in_javascript.html
[28]: http://blog.csdn.net/dhp1027/article/details/7725653
[29]: http://www.cnblogs.com/lhb25/p/web-development-mode-evolve.html
[30]: http://www.ruanyifeng.com/blog/2015/02/mvcmvp_mvvm.html
[31]: http://kb.cnblogs.com/page/196448/
[32]: http://blog.csdn.net/a19881029/article/details/9465663
[33]: http://blog.csdn.net/lfy9608110935/article/details/8302306
[34]: http://www.ruanyifeng.com/blog/2014/05/restful_api.html
[35]: http://kb.cnblogs.com/page/512047/
[36]: http://www.jianshu.com/p/70f0a2d8024e
[37]: http://www.jianshu.com/p/6f6efaed11b1
[38]: http://blog.csdn.net/textboy/article/details/51163452
[39]: http://www.cnblogs.com/frchen/p/5740606.html
[40]: http://www.cnblogs.com/patrick0715/p/5957387.html
[41]: https://segmentfault.com/a/1190000003063859
[42]: http://blog.csdn.net/windcao/article/details/25773219
[43]: http://www.ruanyifeng.com/blog/2015/12/git-workflow.html
[44]: http://www.cnblogs.com/lcngu/p/5309101.html
[45]: http://xiaorui.cc/2015/07/13/python%E4%BD%BF%E7%94%A8master-worker%E7%AE%A1%E7%90%86%E6%A8%A1%E5%9E%8B%E5%BC%80%E5%8F%91%E6%9C%8D%E5%8A%A1%E7%AB%AF/