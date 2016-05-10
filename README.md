# formvalid

# 介绍
*  写一个表单验证，感觉写的挺麻烦，虽然网上也有大量的插件，但还是想自己写一个。
*  功能强大，使用简单
*  内置两种 错误提示方式，支持 自定义错误提示
*  表单验证成功，有回调函数，失败也有相应回调

# 使用
原生js操控DOM有点繁琐，借助jQuery.
可直接下载使用，或者习惯 amd，cmd规范的使用模块引入，记得修改 jQuery路径即可。


# demo
```javascript
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
# params说明
- data是一个 对象，key值就是要验证项的 name属性值
	* rule: 每一项的验证规则，用正则表示
	* msg: 如果不符合验证规则，错误提示信息
- tipType: 错误信息显示方式，内置两种类型: 0 表示 弹框，1 表示 右侧小提示
		   可以自定义显示，为函数,function (form, el, msg){}
		   form: 当前表单
		   el: 当前验证元素
		   msg: 错误提示信息
- errorClassName: 验证失败，给当前验证元素添加错误样式class，默认 "invalid"
- success: 表单验证成功要执行的回调函数
- error: 表单验证失败要执行的回调函数