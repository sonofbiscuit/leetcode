# 要求
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。

给出两个整数 x 和 y，计算它们之间的汉明距离。

**注意**
0 ≤ x, y < 2<sup>31</sup>.
<p><h4>实例</h4>
	<pre>
**输入**： x = 1, y = 4
**输出**: 2
**解释**：
1   (0 0 0 1)
4   (0 1 0 0)
       ↑   ↑
上面的箭头指出了对应二进制位不同的位置.
	</pre>
<p/>
————————————————————————————————
**C++**
<pre>
<code>
	class Solution {
public:
    int hammingDistance(int x, int y) {
        int z=x^y;//yihuo
        int count=0;
        while(z){
            count++;
            z&=z-1;
        }
        return count;
    }
};
</code>
</pre>

**JAVA**
<pre>
<code>
class Solution {
    public int hammingDistance(int x, int y) {
        int z=x^y;//异或
        int count=0;
        while(z!=0){
            count++;
            z&=z-1;//同或
        }
        return count;
    }
}
</code>
</pre>
### 解释
* 另外一种方法，可以拆开分别比较。
* 此处使用的是异或与同或，z=x^y可以得到不同位次为1，z&=z-1可以使二进制的最后一位1变为0，即有几个1就循环几次，count+1几次，最后输出count，即为不同位的数量。
