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
    - $weight[rootA] = \frac{1}{weight[a]} \times k \times weight[b]$、$weight[b] = b / rootB$