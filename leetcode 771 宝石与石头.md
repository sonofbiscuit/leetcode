# 要求
给定字符串J 代表石头中宝石的类型，和字符串 S代表你拥有的石头。 S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。

J 中的字母不重复，J 和 S中的所有字符都是字母。字母区分大小写，因此"a"和"A"是不同类型的石头。

<p><h4>实例</h4>
	<pre>
**输入**： J = "aA", S = "aAAbbbb"
**输出**: 3
	</pre>
<p/>
————————————————————————————————
<pre>
<code>
int numJeweIsInStones(String J,String S){
	char sArr[] = S.toCharArraya();
	char jArr[] = J.toCharArray();  
        int list[] = new int['z'-'A'];  
        int sum = 0;  
        for(char s:sArr){  
            list[s-'A']++;  
        }  
        for(char j:jArr){  
            sum += list[j-'A'];  
        }  
        return sum;  
}
</code>
</pre>

#解释
'z'-'A'，z在ASCII码表中为122，A为65，即z-A表示了a-z A-Z的总长度。list[s-'A']++表示当前字符串减去最小的ASCII码并且加1，这样对应的数组位置就为1，例如a为97，减去A65，则有list[32]==1。得到对应位次，再用j相减，例子处j为aA,比如为a时，list[a-'A']=list[32],该位为1，则sum=sum+1。其余同！~
