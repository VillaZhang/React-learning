React 允许将代码封装成组件（component），然后在网页中插入这个组件。`React.createClass `方法就用于生成一个组件类：

````
var HelloMessage = React.createClass({
  render: function() {
    return <h1>Hello {this.props.name}</h1>;
  }
});

ReactDOM.render(
  <HelloMessage name="John" />,
  document.getElementById('example')
);
````

上面代码中，变量 `HelloMessage` 就是一个组件类。模板插入 `<HelloMessage />` 时，会自动生成 `HelloMessage` 的一个实例（下文的"组件"都指组件类的实例）。所有组件类都必须有自己的 `render `方法，用于输出组件。
注意，组件类的第一个字母必须大写，否则会报错，比如`HelloMessage`不能写`helloMessage`。另外，组件类只能包含一个顶层标签，否则也会报错.

````
var HelloMessage = React.createClass({
  render: function() {
    return <h1>
      Hello {this.props.name}
    </h1><p>
      some text
    </p>;
  }
});
````
上面代码会报错，因为`HelloMessage`组件包含了两个顶层标签：`h1`和`p`。

组件的用法与原生的 HTML 标签完全一致，可以任意加入属性，比如 `<HelloMessage name="John"> `，就是 `HelloMessage` 组件加入一个 `name` 属性，值为 `John`。组件的属性可以在组件类的 `this.props `对象上获取，比如 `name` 属性就可以通过` this.props.name` 读取。上面代码的运行结果如下。

![image](http://image.beekka.com/blog/2015/bg2015033108.png)

