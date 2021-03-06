用户在表单填入的内容，属于用户跟组件的互动，所以不能用` this.props` 读取(只能读取组件的属性)。
````
var Input = React.createClass({
  getInitialState: function() {
    return {value: 'Hello!'};
  },
  handleChange: function(event) {
    this.setState({value: event.target.value});
  },
  render: function () {
    var value = this.state.value;
    return (
      <div>
        <input type="text" value={value} onChange={this.handleChange} />
        <p>{value}</p>
      </div>
    );
  }
});

ReactDOM.render(<Input/>, document.body);
````

上面代码中，文本输入框的值，不能用 `this.props.value `读取，而要定义一个 `onChange `事件的回调函数，通过` event.target.value` 读取用户输入的值。`textarea` 元素、`select`元素、`radio`元素都属于这种情况，更多介绍请参考官方文档。

---

### 注：
`this.props.<name>`是对组件属性的读取，不能用在用户与组件的实时互动上。