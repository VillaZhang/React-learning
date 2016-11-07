在正常的html代码中，含有React语法的代码必须放在`<script>` 标签的 `type` 属性为 `text/babel`中，因为这是特有的JSX语法，与JavaScript不兼容，

其次，需要引用三个库，`react.js` 、`react-dom.js` 和 `Browser.js` ，它们必须首先加载。其中，`react.js` 是 React 的核心库，`react-dom.js` 是提供与 DOM 相关的功能，`Browser.js` 的作用是将 JSX 语法转为 JavaScript 语法，这一步很消耗时间，实际上线的时候，应该将它放到服务器完成。

或者直接使用CDN
````
<script src="https://unpkg.com/react@latest/dist/react.js"></script>
<script src="https://unpkg.com/react-dom@latest/dist/react-dom.js"></script>
<script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>
````

其中`babel.min.js`起到的作用和`browser.js`作用一样，均为将 JSX 语法转为 JavaScript 语法。