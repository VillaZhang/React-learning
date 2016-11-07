组件的属性可以接受任意值，字符串、对象、函数等等都可以。有时，我们需要一种机制，验证别人使用组件时，提供的参数是否符合要求。
组件类的`PropTypes`属性，就是用来验证组件实例的属性是否符合要求。

````
var MyTitle = React.createClass({
  propTypes: {
    title: React.PropTypes.string.isRequired,
  },

  render: function() {
     return <h1> {this.props.title} </h1>;
   }
});
````

上面的`Mytitle`组件有一个`title`属性。`PropTypes `告诉 React，这个` title` 属性是必须的，而且它的值必须是字符串。现在，我们设置` title` 属性的值是一个数值。
````
var data = 123;

ReactDOM.render(
  <MyTitle title={data} />,
  document.body
);
````

这样一来，`title`属性就通不过验证了。控制台会显示一行错误信息（只是warning，网页上还是会照常显示）。

````
Warning: Failed propType: Invalid prop `title` of type `number` supplied to `MyTitle`, expected `string`.
````

更多的`PropTypes`设置，可以查看官方文档。

此外，`getDefaultProps` 方法可以用来设置组件属性的默认值。
````
var MyTitle = React.createClass({
  getDefaultProps : function () {
    return {
      title : 'Hello World'
    };
  },

  render: function() {
     return <h1> {this.props.title} </h1>;
   }
});

ReactDOM.render(
  <MyTitle />,
  document.body
);
````

上面代码会输出"Hello World"。


---

### 注：
本实验采用React-15.3.1版本，必须引入`react-with-addons.js`文件，否则在chrome浏览器中不会出现warning警告。以及需对jsx语言进行编译，使用`babel-6.15.0`进行编译，引用地址为`	<script src="https://unpkg.com/babel-standalone@6.15.0/babel.js"></script>`。