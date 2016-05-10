# formvalid

# 介绍
*  写一个表单验证，感觉写的挺麻烦，虽然网上也有大量的插件，但还是想自己写一个。
*  功能强大，使用简单
*  内置两种 错误提示方式，支持 自定义错误提示
*  表单验证成功，有回调函数，失败也有相应回调

# 使用
原生js操控DOM有点繁琐，借助jQuery.
可直接下载使用，或者习惯 amd，cmd规范的使用模块引入，记得修改 jQuery路径即可。

```javascript
demo
 var elForm = $("form");
var ops = {
	data: {
		"name": {
			rule: /\w+/,
			msg: "请输入您的name"
		},
		"age": {
			rule: /^\d{1,3}$/,
			msg: "请输入您的age"
		},
		"sex": {
			rule: /\w+/,
			msg: "请输入您的sex"
		},
		"job": {
			rule: /\w+/,
			msg: "请输入您的job"
		}
	},
	tipType: 1,
	errorClassName: "invalid",
	success: function (){
		alert("success");
	},
	error: function (){

	}
}
var myForm = elForm.formValid(ops);
```
