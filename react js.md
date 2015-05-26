react js

http://www.ruanyifeng.com/blog/2015/03/react.html
https://github.com/ruanyf/react-demos
React 入门实例教程

https://github.com/tastejs/todomvc
http://todomvc.com/
http://todomvc.com/examples/react/#/
React js todoMVC


https://github.com/facebook/flux/tree/master/examples/flux-todomvc
Flux TodoMVC Example


http://facebook.github.io/react/docs/getting-started.html




			var activeTodoCount = todos.reduce(function (accum, todo) {
				return todo.completed ? accum : accum + 1;
			}, 0);




React 入门实例教程
=============

https://github.com/ruanyf/react-demos

> git clone git@github.com:ruanyf/react-demos.git

{}
this.props
this.props.children
.map()

React.findDOMNode()
this.refs.[refName]

this.state
getInitialState()
this.setState()

event.target.value

组件的生命周期:
Mounting
Updating
Unmounting

五种处理函数:
componentWillMount()
componentDidMount()
componentWillUpdate(object nextProps, object nextState)
componentDidUpdate(object prevProps, object prevState)
componentWillUnmount()

componentWillReceiveProps(object nextProps)
shouldComponentUpdate(object nextProps, object nextState)


React js todoMVC
=============

http://todomvc.com/examples/react/#/

路由
-----
	componentDidMount: function () {
		var setState = this.setState;
		var router = Router({
			'/': setState.bind(this, {nowShowing: app.ALL_TODOS}),
			'/active': setState.bind(this, {nowShowing: app.ACTIVE_TODOS}),
			'/completed': setState.bind(this, {nowShowing: app.COMPLETED_TODOS})
		});
		router.init('/');
	},

DOM交互
-----
	var val = this.refs.newField.getDOMNode().value.trim();	


reduce方法
-----
	var activeTodoCount = todos.reduce(function (accum, todo) {
		return todo.completed ? accum : accum + 1;
	}, 0);

组件间参数/事件传递
-----
	<TodoItem
		key={todo.id}
		todo={todo}
		onToggle={this.toggle.bind(this, todo)}
		onDestroy={this.destroy.bind(this, todo)}
		onEdit={this.edit.bind(this, todo)}
		editing={this.state.editing === todo.id}
		onSave={this.save.bind(this, todo)}
		onCancel={this.cancel}
	/>

render
-----
- UI和model的交互都是通过TodoApp进行的，而不是TodoItem。TodoItem的改动通过事件传递给TodoApp，TodoApp更新model。所以有很多事件传递。
- model的任何改动都会调用app.TodoModel.prototype.inform（），通知TodoApp重新render。但是，由于Recat.js使用了virtual DOM，所以只需要操作改变的DOM节点。

http://www.syncano.com/reactjs-reasons-why-part-1/
6 REASONS WHY WE LOVE REACT.JS

http://todomvc.com/examples/react/examples/react/js/app.jsx
	function render() {
		React.render(
			<TodoApp model={model}/>,
			document.getElementById('todoapp')
		);
	}

	model.subscribe(render);
	render();

http://todomvc.com/examples/react/examples/react/js/todoItem.jsx
	app.TodoModel.prototype.subscribe = function (onChange) {
		this.onChanges.push(onChange);
	};

	app.TodoModel.prototype.inform = function () {
		Utils.store(this.key, this.todos);
		this.onChanges.forEach(function (cb) { cb(); });
	};	


React.addons.classSet()
-----
通过设置class来显示/隐藏input

		render: function () {
			return (
				<li className={React.addons.classSet({
					completed: this.props.todo.completed,
					editing: this.props.editing
				})}>

shouldComponentUpdate()
-----
		/**
		 * This is a completely optional performance enhancement that you can
		 * implement on any React component. If you were to delete this method
		 * the app would still work correctly (and still be very performant!), we
		 * just use it as an example of how little code it takes to get an order
		 * of magnitude performance improvement.
		 */
		shouldComponentUpdate: function (nextProps, nextState) {
			return (
				nextProps.todo !== this.props.todo ||
				nextProps.editing !== this.props.editing ||
				nextState.editText !== this.state.editText
			);
		},


Flux TodoMVC Example
=============

https://github.com/facebook/flux/tree/master/examples/flux-todomvc







！！！
https://github.com/codemirror/CodeMirror
http://codemirror.net/


http://prettydiff.com/


https://github.com/facebook/react/wiki/Complementary-Tools

http://browserify.org/



https://github.com/react-component/progress






1. module, AMD\CMD, require js	
	Browserify Webpack ?

2. promise, defered,  	

3. $.ajax	
	error handler

4. route 

5. mvc/mvvm/framework, 					
	flux ?

6. event system


7. template 


developing a react edge



React js Getting Started
=============

npm install -g react-tools
jsx --watch src/ build/




https://github.com/facebook/flux/tree/master/examples/flux-todomvc




https://facebook.github.io/react/docs/advanced-performance.html
Advanced Performance


http://www.vccoo.com/v/c8077f

React.js大型复杂应用实战：Codecademy

http://www.cnblogs.com/shanyou/p/4472862.html
初探ReactJS.NET 开发



http://www.farennikov.com/2014/04/building-react-js-with-grunt/#.VV7Nffmqqko
Building React.js with Grunt


http://xinranliu.me/2015-01-30-some-understanding-about-flux/
React Flux的一些理解(React Flux入门教程)

http://undefinedblog.com/react-router/
ReactRouter 使用指南

!!
http://undefinedblog.com/facebook-flux/
浅析 Facebook Flux 架构


https://github.com/h5bp/html5-boilerplate

http://www.w3cplus.com/html5/html5-boilerplate.html
HTML 5 Boilerplate 5.0 中文文档


https://github.com/jakearchibald/es6-promise
http://www.html5rocks.com/en/tutorials/es6/promises
JavaScript Promises


https://thewayofcode.wordpress.com/tag/jquery-deferred-broken/
JAVASCRIPT PROMISES AND WHY JQUERY IMPLEMENTATION IS BROKEN

1. function composition: chainable async invocations
2. error bubbling




http://es6.ruanyifeng.com/
ECMAScript 6入门

http://www.cnblogs.com/Wayou/p/es6_new_features.html
ES6新特性概览

http://www.cnblogs.com/ziyunfei/archive/2012/09/17/2688829.html
[译]shim和polyfill有什么区别?


https://github.com/es-shims/es5-shim
es5-shim


http://fex.baidu.com/

http://www.cnblogs.com/dojo-lzz/p/4526896.html?utm_source=tuicool
初探ECMAScript6




http://www.tuicool.com/articles/QZVzeuU
Browserify —— 利用Node.js实现JS模块化加载
http://baike.baidu.com/item/browserify?fr=aladdin

http://blog.jobbole.com/78825/
browserify运行原理分析




http://blog.jobbole.com/75874/
JavaScript构建（编绎）系统大比拼：Grunt vs. Gulp vs. NPM

http://blog.jobbole.com/81007/
Gulp， 比Grunt更好用的前端构建工具

http://blog.jobbole.com/81007/
Gulp相对于Grunt的优势

http://blog.jobbole.com/51586/
自动化任务运行器 Grunt 迅速上手


!!!
http://blog.jobbole.com/80338/
gulp入門指南

http://blog.jobbole.com/62098/
Yeoman：Web 应用开发流程与工具


http://blog.jobbole.com/79075/
前端代码规范 及 最佳实践


http://blog.jobbole.com/47185/
如何构建自动化的前端开发流程





http://blog.jobbole.com/8087/
Limu：JavaScript的那些书

http://blog.jobbole.com/28681/
初步认识 LESS

http://blog.jobbole.com/24671/
LESS介绍及其与Sass的差异

http://blog.jobbole.com/1151/
阮一峰：jQuery官方基础教程笔记




http://blog.jobbole.com/1115/
再谈Yahoo关于性能优化的N条规则

http://blog.jobbole.com/1022/
9个实用的Javascript代码高亮脚本

http://blog.jobbole.com/79601/
深入了解 ES6 生成器



http://blog.jobbole.com/79203/

jQuery 3.0：下一代的 jQuery


http://blog.jobbole.com/79075/
前端代码规范 及 最佳实践


http://blog.jobbole.com/78738/
BAT及各大互联网公司2014前端笔试面试题：JavaScript篇


http://blog.jobbole.com/78281/
高性能Javascript：高效的数据访问

http://blog.jobbole.com/77703/
当 React 遇上 KendoUI

http://blog.jobbole.com/76500/
跟着 8 张思维导图学习 Javascript

http://blog.jobbole.com/76141/
组件化的Web王国

http://blog.jobbole.com/76032/
编写可维护的CSS

http://blog.jobbole.com/76030/
CSS设计模式：OOCSS 和 SMACSS





http://blog.jobbole.com/66699/
JavaScript 的常见“陷阱”

http://blog.jobbole.com/66441/
JavaScript中的原型和继承


http://blog.jobbole.com/64771/
JavaScript基础工具清单





!!!
http://blog.jobbole.com/78946/
AngularJS开发人员最常犯的10个错误


http://blog.jobbole.com/62249/
AngularJS 指令实践指南（一）

http://blog.jobbole.com/62999/
AngularJS 指令实践指南（二）

http://blog.jobbole.com/51558/
构建自己的AngularJS（1）：Scope和Digest


http://blog.jobbole.com/48593/
七步从Angular.JS菜鸟到专家（2）：Scopes

http://blog.jobbole.com/51178/
卡通方式趣解 AngularJS 中的 promise

http://blog.jobbole.com/51180/
优化AngularJS：1200毫秒到35毫秒的蜕变

http://blog.jobbole.com/48979/
5个示例带你学习AngularJS

http://blog.jobbole.com/52857/
AngularJS 中的一些坑

http://blog.jobbole.com/80634/
AngularJS最佳编码实践指南


http://blog.jobbole.com/tag/ie-css-bug/



http://blog.jobbole.com/49084/
JavaScript 垃圾回收

http://blog.jobbole.com/44772/
JavaScript的一些常见误区

http://blog.jobbole.com/43663/
从零开始写JavaScript框架（二）

http://blog.jobbole.com/43649/
从零开始写JavaScript框架（一）

http://blog.jobbole.com/40409/
深入研究JavaScript的Module模式

http://blog.jobbole.com/32572/
JavaScript 项目优化总结

http://blog.jobbole.com/58032/
理解 JavaScript 中的 Function.prototype.bind

http://blog.jobbole.com/66699/
JavaScript 的常见“陷阱”

http://blog.jobbole.com/67347/
JavaScript中this的工作原理以及注意事项

http://blog.jobbole.com/40409/
深入研究JavaScript的Module模式

http://blog.jobbole.com/70745/
理解JavaScript的函数调用和this






$q
$http
module




http://www.w3ctech.com/topic/142

最近一次项目的总结



http://my.oschina.net/ilivebox/blog?catalog=3290963


學習臉書的 React.js 系列






javascript模块化


http://www.ruanyifeng.com/blog/2015/05/commonjs-in-browser.html
浏览器加载 CommonJS 模块的原理与实现
Browserify 


http://www.ruanyifeng.com/blog/javascript/
Javascript模块化编程（三）：require.js的用法（47@2012.11.07）
Javascript模块化编程（二）：AMD规范（35@2012.10.30）
Javascript模块化编程（一）：模块的写法（47@2012.10.26）


http://www.zhihu.com/question/20351507/answer/14859415
AMD 和 CMD 的区别有哪些？

http://segmentfault.com/a/1190000000733959
详解JavaScript模块化开发

http://www.tuicool.com/articles/nYVj2i
前端模块管理器简介


！！！
http://c.jinhusns.com/cms/c-1089
基于ES6，使用React、Webpack、Babel构建模块化JavaScript应用


http://npm.taobao.org/


https://github.com/hughsk/uglifyify
https://github.com/hughsk/envify
！！！
https://github.com/JedWatson/classnames
http://facebook.github.io/jest/
https://facebook.github.io/flux/docs/overview.html
！！！
http://facebook.github.io/immutable-js/

http://facebook.github.io/react/docs/events.html
http://facebook.github.io/react/tips/references-to-components.html


！！！
http://zhuanlan.zhihu.com/FrontendMagazine/19906158
结合 React，Flux & Web Components

http://zhuanlan.zhihu.com/FrontendMagazine/19900243
Flux 傻瓜教程

http://zhuanlan.zhihu.com/FrontendMagazine/19896745
ReactJS 傻瓜教程

https://github.com/facebook/react/wiki/Complementary-Tools

！！！
https://github.com/facebook/react/tree/master/docs/docs
中文文档


http://ju.outofmemory.cn/entry/102167
react入门——环境搭建

http://www.kuqin.com/shuoit/20141221/344013.html
WebPack：更优秀的模块依赖管理工具，及require.js的缺陷

https://github.com/webpack/webpack


!!!!
http://reactjs.cn/react/docs/getting-started.html
中文

http://react-china.org/
中文社区


http://www.infoq.com/cn/articles/subversion-front-end-ui-development-framework-react
颠覆式前端UI开发框架：React

http://www.infoq.com/cn/articles/react-art-of-simplity
深入浅出React（一）：React的设计哲学 - 简单之美

http://www.cnblogs.com/yunfeifei/p/4486125.html?utm_source=tuicool
http://www.tuicool.com/articles/ii6Nn2
一看就懂的ReactJs入门教程-精华版

！！！
https://github.com/enaqx/awesome-react#flux-tutorials
Awesome React

http://react-china.org/collections/



http://segmentfault.com/a/1190000000693651
React.js 概览





http://www.cnblogs.com/yunfeifei/p/3850440.html
数据库SQL优化大总结之 百万级数据库优化方案



！！！
https://signalvnoise.com/posts/3124-give-it-five-minutes
Give it five minutes



http://www.csdn.net/article/2015-02-13/2823956-angular-vs-re
我由Angular转向React，为什么？





















































































































