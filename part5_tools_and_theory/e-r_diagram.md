> TODO: 缺少图片描述

# E-R图

## 简介

ER模型，全称为实体联系模型（Entity-relationship model）或实体关系模型或实体联系模式图（Entity Relationship Diagram）。

- **矩形表示实体（Entity）类型，并且在矩形框内写明实体名；**
- **椭圆表示实体的属性（Attribute），并用无向边将其与相应的实体型连接起来；**
- **菱形表示实体类型间的关系（relationship），在菱形框内写明联系名，并用无向边分别与相关实体型连接，同时在无向边旁标上联系的类型（1:1,1:n或m:n）。**

联系可分为以下 3 种类型：

- 一对一联系(1 ∶ 1)
例如，一个学校只有一个校长，一个校长只在一个学校做校长，则校长与学校“执教”的联系为一对一。
- 一对多联系(1 ∶ N)
例如，教师可能教多门课程，但是每个固定课程只能由一位教师授课，即是教师与课程之间存在一对多“教”的联系。
- 多对多联系(M ∶ N)
例如，一个学生可以学多门课程，同时一门课程可以有多个学生上课，即是学生与课程间的“学”的联系是多对多的。

> 联系也可能有属性。例如，学生“ 学” 某门课程所取得的成绩，既不是学生的属性也不是课程的属性，而“ 成绩” 既依赖于某名特定的学生又依赖于某门特定的课程，所以它是学生与课程之间的联系“ 学”的属性。

![e-r_diagram](../../images/e-r/e-r_diagram.jpg)

## E-R图的画法

### 作图步骤

 - 确定所有的实体集合
 - 选择实体集应包含的属性
 - 确定实体集之间的联系
 - 确定实体集的关键字，用下划线在属性上表明关键字的属性组合
 - 确定联系的类型，在用线将表示联系的菱形框联系到实体集时，在线旁注明是1或n(多）来表示联系的类型

### 设计步骤

- 根据需求分析结果对数据抽象然后选择好局部应用

	根据系统的具体情况，在多层的数据流图中选择一个适当层次的数据流图，让这组图中每一部分对应一个局部应用，我们即可以以这一层次的数据流图为出发点，设计分E-R图。

- 逐一设计各个分E-R图。

	每个局部应用都对应了一组数据流图，局部应用涉及的数据都已经收集在数据字典中。现在将这些数据从数据字典中抽取出来，参照数据流图， 标定局部应用中的实体、实体的属性、标识实体的码，  确定实体之间的联系及其类型（1：1、1：n、m：n）。

- 合并分E-R图，生成初步E-R图
  各分E-R图合并时会遇到的冲突主要有三类：

  - **a．属性冲突**

  		- 属性域冲突，即属性值的类型、取值范围或取值集合不同。例如：属性“零件号”有的定义为字符型，有的为数值型。
    	- 属性取值单位冲突。例如：属性“重量”有的以克为单位，有的以公斤为单位。

  - **b．命名冲突**
    	- 同名异义。不同意义对象相同名称。
    	- 异名同义（一义多名）。同意义对象不相同名称。“项目”和“课题”

  - **c．结构冲突**

   		- 同一对象在不同应用中具有不同的抽象。例如"课程 "在某一局部应用中被当作实体，而在另一局部应用中则被当作属性。
    	- 同一实体在不同局部视图中所包含的属性不完全相同，或者属性的排列次序不完全相同。
    	- 实体之间的联系在不同局部视图中呈现不同的类型。例如实体E1与E2在局部应用A中是多对多联系，而在局部应用B中是一对多联系；又如在局部应用X中E1与E2发生联系，而在局部应用Y中E1、E2、E3三者之间有联系。解决方法是根据应用的语义对实体联系的类型进行综合或调整。

- 修改重构

	生成基本E-R图分E-R图经过合并生成的是初步E-R图。之所以称其为初步E-R图，是因为其中可能存在冗余的数据和冗余的实体间联系，即存在可由基本数据导出的数据和可由其他联系导出的联系。冗余数据和冗余联系容易破坏数据库的完整性，给数据库维护增加困难，因此得到初步E-R图后，还应当进一步检查E-R图中是否存在冗余，如果存在，应设法予以消除。修改、重构初步E-R图以消除冗余，主要采用分析方法。除此外，还可以用规范化理论来消除冗余。
