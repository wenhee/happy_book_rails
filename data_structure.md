
数据结构.

在大学里, 考研 :  数据结构, 操作系统, 计算机组成原理.

数据结构:

1. 需要写具体的底层代码
2. 会用就行. (往往是第二种)

# 定义

是一种结构. 可以有特定的方法,来操作这些结构.

## 数组

a = [1,2,3]

1. size.  (获取数组的长度)   # => 3

2. [] (最常用的)
a[0] = 1
a[1] = 2
a[2] = 3

3. pop  (不常用,  因为我们在实战当中, 不轻易改变某个变量的结构.) 取出最后一个元素, 并且,数组发生改变,(少了一个元素)

irb(main):003:0> a = [1,2,3]
=> [1, 2, 3]
irb(main):004:0> a.pop
=> 3
irb(main):005:0> a
=> [1, 2]


4. push (也不常用)  pop的反义词.

irb(main):007:0> b.push 200
=> [100, 200]
irb(main):008:0> b
=> [100, 200]

往往对它做循环操作.



## Hash  哈希

由 key, value组成的结构.  也有很多语言, 管它叫 字典( dictionary )

```

a = {
   :name => 'Jim',
   :sex => 'male'
   # key => value
}

```

核心方法,只有: []

irb(main):014:0> my_hash  = { 'name' => 'jim', :age => 28}
=> {"name"=>"jim", :age=>28}
irb(main):015:0> my_hash['name']
=> "jim"
irb(main):016:0> my_hash[:age]
=> 28


还有其他的方法,但是不常用, 包括:

keys  , 返回所有的keys,
key?  ,  来判断, 某个字符串, 是否是该hash的可以

所有的key, 都是完全不一样的. 不会出现 重复的key.

用在无数的地方.  我能想到的是:

１．参数
2. 作为缓存(cache) 的一种实现.
3. 在rails中 , 会大量的用到hash.


## 集合 Set


[1,2,3] 是一个数组, 也是一个集合.

[2,2,4]  是一个数组, 不是一个集合.

集合: 可以认为, 是由多个元素组成的 数据结构. 特点:
1. 集合中的元素, 没有重复的.
2. 集合中元素, 顺序是打乱的.

irb(main):030:0* my_set = Set.new
=> #<Set: {}>
irb(main):031:0> my_set.add('a')
=> #<Set: {"a"}>
irb(main):032:0> my_set.add('b')
=> #<Set: {"a", "b"}>
irb(main):033:0> my_set.add('c')
=> #<Set: {"a", "b", "c"}>
irb(main):034:0> my_set.add('c')
=> #<Set: {"a", "b", "c"}>


就几个方法:

add .  往集合里添加元素
to_a   转换成 数组


做web开发, 很少用到. 但是, 它是非常重要的数据结构.


## 树

例如:

            a
         /  |  \
        b   c   d

        a:  叫父节点.   在最顶端的时候, 叫 root(根)
        b,c,d: 子节点, 或者叫 叶子


a.children  列出所有的子节点  # =>  [b, c, d]

a.parent 列出父类的节点.

XML 就是一种非常典型的 树状结构

<div>
   <div> ... </div>
   <div> ... </div>
</div>

在web开发中, 后端很少用到 树, 在前端, jquery, css选择器中, 会大量的用到.

而且,在jQuery中, 会让我们非常方便的操作这个树 .

## 二叉树 和 满二叉树.

二叉树:  所有节点中,每个节点, 只有一个 左儿子, 和右儿子.

满二叉树:  树中, 所有的节点,都必须是两个儿子都有.

重要性: 在排序的时候,特别重要.


几乎用不上.

## 个人认为: 排序几乎用不上.

方法论:  平时, 会看API, 会用,就足够了.

需要的时候,再去学习.


