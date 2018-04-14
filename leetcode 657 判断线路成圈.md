# 要求
初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一个圆圈，换言之就是判断它是否会移回到原来的位置。

移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。


<p><h4>示例1:</h4>
	<pre>
**输入**： "UD"
**输出**: true
	</pre>
<p/>
<p><h4>示例2:</h4>
	<pre>
**输入**： "LL"
**输出**: false
	</pre>
<p/>
————————————————————————————————
**JAVA**
<pre>
<code>
class Solution {
    public boolean judgeCircle(String moves) {
        char movearr[]=moves.toCharArray();
        int x=0;
        int y=0;
        for(char w:moves.toCharArray()){
            if(w=='U') y++;
            else if(w=='D') y--;
                else if(w=='L')x--;
                    else if(w=='R')x++;
        }
        return x==0&&y==0;
    }
}
</code>
</pre>
