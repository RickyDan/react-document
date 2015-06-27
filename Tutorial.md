##展示数据
. 在UI层上最根本的东西就是展示数据。React让展示数据变得非常轻松并且自动定位并更新界面中数据变化的地方

##开始React之旅
. 让我们先来看一个简单的例子。创建一个经典的Hello-world的React实例

    <!DOCTYPE HTML>
    <html>
        <head>
            <title>Hello React</title>
            <script src="https://fb.me/react-0.13.3.js"></script>
            <script src="https://fb.me/JSXTransformer-0.13.3.js"></script>
        </head>
        <body>
            <div id="example"></div>
            <script type="text/jsx">
                //这里写你的代码
                var HelloWorld = React.createClass({
                    render: function() {
                        return (
                            <p>
                                Hello, <input type="text" placeholder="Your name here" />!
                                It is {this.props.date.toTimeString()}
                            </p>
                        );
                    }
                });

                setInterval(function() {
                    React.render(
                        <HelloWorld date={new Date()} />,
                        document.getElementById('example')
                    );
                }, 500);
            </script>
        </body>
    </html>
. 在接下来的文档当中，我们只会聚焦在javascript代码中，并且假定它已经成功插入像上述例子的模板中，使用JSX置换掉占位符中的文字。

##React的更新
. 在浏览器上打开hello-react.html然后在文本输入框中输入你的名字。注意到React仅仅更新UI层上时间数据的变化-任何在文本框的输入都保持不变，即使你没有写任何代码去控制这个行为.React会自动帮你做这些事情.
. React并没有去操纵DOM除非必须要这么做。它使用的是更快速的，虚拟的DOM去执行和计算出最高效率的DOM变更。
. 输入的文字作为这个组件的属性,通过使用一种称为JSX的语法机制。你应该把这些属性当成组件中不可变的，并且永远不要去改写它。
