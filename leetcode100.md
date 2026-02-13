# Java-leecode100
## leecode100题解学习笔记记录
### 399.除法求值
- 通过带权并查集维护变量之间的关系
  - 选一个作为根节点（标准单位）
  - 维护两个Map:
    - parent:记录父节点
    - weight：记录我/父节点的值
  - 路径压缩：
    - 所有节点指向根节点，路径压缩中，权重是累乘的
  - 合并节点：
    - 合并两个结合，将两个节点的根节点挂载到一起
    - $weight[rootA] = \frac{1}{weight[a]} \times k \times weight[b] 、 weight[b] = b / rootB $

### 2.两数相加
- 递归
  - 需要注意，结束条件是没有相加的数也没有进位
  - 判断一个对象是否为null，必须是判断不等于null，而不是判断等于null
  - 为什么递归函数里，同一个名字的变量在递归中不会被覆盖？
    - 因为在函数内定义的变量，其作用域只作用于这一个函数，函数结束变量就失效了。
### 394.字符串解码
- 方法一、递归
- 方法二、辅助栈法
  - 两个辅助栈：数字栈、字符串栈
    - 一个存循环次数，一个存字符串
- 依次读取字符串转数字的方法：
    - ```java 
        int ret = 0;
        while (ptr < src.length() && Character.isDigit(src.charAt(ptr))) {
        ret = ret * 10 + src.charAt(ptr++) - '0';
        }
        return ret;
### 347.前k个高频元素
