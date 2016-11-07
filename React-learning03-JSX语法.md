 JSX 的基本语法规则：遇到 HTML 标签（以` < `开头），就用 HTML 规则解析；遇到代码块（以` {` 开头），就用 JavaScript 规则解析。
````
var names = ['Alice', 'Emily', 'Kate'];

ReactDOM.render(
  <div>
  {
    names.map(function (name) {
      return <div>Hello, {name}!</div>
    })
  }
  </div>,
  document.getElementById('example')
);
````
结果如下：

![image](http://image.beekka.com/blog/2015/bg2015033106.png)

若赋给`arr`变量是一个数组，结果 JSX 会把它的所有成员，添加到模板，如下：
````
var arr = [
  <h1>Hello world!</h1>,
  <h2>React is awesome</h2>,
];
ReactDOM.render(
  <div>{arr}</div>,
  document.getElementById('example')
);
````
结果如下：

![image](http://image.beekka.com/blog/2015/bg2015033107.png)

