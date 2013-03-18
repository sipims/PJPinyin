# PJPinyin
===================

PJPinyin是由 闲耘™((@hotoo <hotoo.cn[AT]gmail.com>)) 的代码根据大量外部数据集取字频最高读音而去除多音字后生成的新的node.js/web拼音转换模块, 解决了原版中无法确定最优组合的问题, 适合不依赖词典时的无多音字拼音转换.

请注意API与原版略有不同: 由于去除了多音字取笛卡尔积部分, 所以不再使用原版中的第二个参数single!


## 安装

<pre>
  npm install PJPinyin
</pre>

Or from source:

<pre>
  git clone git://github.com/peakji/PJPinyin.git
  cd PJPinyin
  npm link
</pre>

## 使用样例

```javascript
	var pinyin = require("./PJPinyin.js");

	console.log(pinyin("游戏"));				// [ 'You', 'Xi' ]

	console.log(pinyin("ni你hao好"));		// [ 'n', 'i', 'Ni', 'h', 'a', 'o', 'Hao' ]

	console.log(pinyin("游戏",''));			// YouXi

	console.log(pinyin("ni你hao好",''));		// niNihaoHao

	console.log(pinyin("游戏",','));			// You,Xi

	console.log(pinyin("ni你hao好",'|'));	// n|i|Ni|h|a|o|Hao
```
