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
