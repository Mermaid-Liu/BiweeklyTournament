# 第七届双周赛试题分析
##  第一题：单行键盘（easy）
### 要点：找到每个单词的位置，记录当前位置，求差取绝对值即可
```
/**
 * @param {string} keyboard
 * @param {string} word
 * @return {number}
 */
let abs=(x)=>{
    if(x<0)return -x
    return x
}
var calculateTime = function(keyboard, word) {
    let n=word.length//记录word的长度
    let position=new Map()//声明一个position记录每个字符的位置
    for(let i=0;i<26;i++){
      //  position[keyboard[i]]=i
       position.set(keyboard[i],i)
    }
    let res=0//结果
    let cur=0//当前位置
    for(let j=0;j<n;j++){
        res+=abs(position.get(word[j])-cur)
        cur=position.get(word[j])
    }
    return res
};
```

