# 要求
给定一个Excel表格中的列名称，返回其相应的列序号。<br>
<code>

    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
    AA -> 27
    AB -> 28
    ...
</code>

**示例 1:**

输入: "A"<br>
输出: 1

**示例 2:**

输入: "AB"<br>
输出: 28

**示例 3:**

输入: "ZY"<br>
输出: 701
————————————————————————————————————

**JAVA**
<pre>
<code>
class Solution {
    public int titleToNumber(String s) {
        char[]array=s.toCharArray();
        int r=0;
        for(int i=0;i&lt;array.length;i++){
            r=26*r+array[i]-'A'+1;
        }
        return r;
    }
}
</code>
</pre>
### 解释
26进制转换为10进制
