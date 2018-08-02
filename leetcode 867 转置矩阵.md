# 要求
给定一个矩阵 A， 返回 A 的转置矩阵。

矩阵的转置是指将矩阵的主对角线翻转，交换矩阵的行索引与列索引

**示例 1：**

输入：[[1,2,3],[4,5,6],[7,8,9]]<br>
输出：[[1,4,7],[2,5,8],[3,6,9]]<br>
**示例 2：**
输入：[[1,2,3],[4,5,6]]<br>
输出：[[1,4],[2,5],[3,6]]

**提示**

**1、** 1 <= A.length <= 1000</br>
**2、** 1 <= A[0].length <= 1000
————————————————————————————————————

**JAVA**
<pre>
<code>
class Solution {
    public int[][] transpose(int[][] A) {
        if(1>A.length || A.length>1000 || 1>A[0].length || A[0].length>1000)
            return null;
        int W=A.length;
        int N=A[0].length;
        int C[][]=new int[N][W];
        for(int i=0;i&lt;A.length;i++){
            for(int j=0;j&lt;A[i].length;j++){
                C[j][i]=A[i][j];
            }
        }
        return C;
    }
}
</code>
</pre>
### 解释
尺寸为 W x N 的矩阵 A 转置后会得到尺寸为 N x W 的矩阵 C，对此有 
C[j][i]=A[i][j]
