### <p align="center">LC1-二叉树的最小深度</p>
### 知识点
知识点: 
- 树


### 描述
求给定二叉树的最小深度。最小深度是指树的根结点到最近叶子结点的最短路径上结点的数量。

### 示例1

```
输入：{1,2,3,4,5}
返回值：2
```

### 我的代码

```Java
//使用队列
public int run(TreeNode root) {
   if(root==null){
         return 0;
   }
   int left  = run(root.left);
   int right  = run(root.right);
   if(left*right >0){
      return (left>right?right:left)+1;
   }else{
      return (left>right?left:right)+1;
   }
}

```
时间复杂度:

空间复杂度:

### 思路和想法
   题目是求二叉树的最小深度 所以需要遍历 而二叉树的遍历分为深度优先遍历和广度优先遍历
   
   很明显深度优先遍历不适合 因为它是偏向于纵深的遍历

   广度优先遍历的实现方式 有队列和递归

   

### 优化以及其他实现方式

可以的话 我会先将二叉树构建成二叉查找树(二叉排序树)
```

```

时间复杂度：
   
空间复杂度：

