### <p align="center">LC2-后缀表达式求值</p>
### 知识点
知识点: 
- 栈

### 描述
计算逆波兰式（后缀表达式）的值
运算符仅包含"+","-","*"和"/"，被操作数可能是整数或其他表达式
例如：

>["20", "10", "+", "30", "*"] -> ((20 + 10) * 30) -> 900
>["40", "130", "50", "/", "+"] -> (40 + (130 / 50)) -> 42

### 示例1
```
输入：["20","10","+","30","*"]
返回值：900
```

### 我的代码
```Java
//栈
class Solution {
    public int evalRPN(String[] tokens) {
        Deque<Integer> stack = new LinkedList<Integer>();
        int n = tokens.length;
        for (int i = 0; i < n; i++) {
            String token = tokens[i];
            if (isNumber(token)) {
                stack.push(Integer.parseInt(token));
            } else {
                int num2 = stack.pop();
                int num1 = stack.pop();
                switch (token) {
                    case "+":
                        stack.push(num1 + num2);
                        break;
                    case "-":
                        stack.push(num1 - num2);
                        break;
                    case "*":
                        stack.push(num1 * num2);
                        break;
                    case "/":
                        stack.push(num1 / num2);
                        break;
                    default:
                }
            }
        }
        return stack.pop();
    }

    public boolean isNumber(String token) {
        return !("+".equals(token) || "-".equals(token) || "*".equals(token) || "/".equals(token));
    }
}

```
时间复杂度:O(n):


空间复杂度:O(n):


### 思路和想法
   基本思路是这样的：使用栈的先入后出的特性来实现 当然也可以使用数组
   
   栈：
   遇到数字就进栈 遇到符号就将栈顶两个数字出栈计算 计算得到的值再进栈 最后栈顶就是我们需要的最终计算结果

   数组：
   需要先构建好数组的大小 而有效的逆波兰式最少也需要拥有两个数字和一个操作数 由此可以得知构建的数组大小为(n+1)/2 且n为奇数
   

### 优化以及其他实现方式
```java
//数组



```
时间复杂度:

空间复杂度: