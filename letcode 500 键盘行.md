# 要求

给定一个单词列表，只返回可以使用在键盘同一行的字母打印出来的单词。键盘如下图所示
![keyboard](https://sonofbiscuit.github.io/leetcode/image/keyboard.png)

<p><h4>示例1:</h4>
	<pre>
**输入**： ["Hello", "Alaska", "Dad", "Peace"]
**输出**: ["Alaska", "Dad"]
	</pre>
<p/>

<p><h4>注意:</h4>
1、你可以重复使用键盘上同一字符。<br>
2、你可以假设输入的字符串将只包含字母。<br>

<pre><code>
class Solution {
    public String[] findWords(String[] words) {
        String[] strs = {"QWERTYUIOP","ASDFGHJKL","ZXCVBNM"};
        Map<Character, Integer> map = new HashMap<>();//前为键值 后为value
        for(int i = 0; i &lt;strs.length; i++){
            for(char c: strs[i].toCharArray()){
                map.put(c, i);
	//put &lt;char,rowIndex> pair into the map
            }
        }
        List&lt;String> res = new LinkedList<>();
        for(String w: words){
            if(w.equals("")) continue;//word为空
            int index = map.get(w.toUpperCase().charAt(0));//转换为大写,获得words的头字母并且返回对应key值
            for(char c: w.toUpperCase().toCharArray()){//遍历words
                if(map.get(c)!=index){//如果word内的元素的key值不为头字母的key值
                    index = -1; 
                    break;
                }
            }
            if(index!=-1) res.add(w);//if index != -1, 存入list res
        }
        return res.toArray(new String[0]);//输出
    }
}
</code></pre>
