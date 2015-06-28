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

##组件就像函数
. React的组件非常简单。你可以把他们想象成携带属性和状态并加载HTML的简单函数。记住这一点，组件就很容易理解了。
. 注意 React的组件只能加载单一的根节点。如果你想加载多层结构的节点，就必须把它覆盖在一个单一的根节点下。

##JSX语法
. 我们相信组件化是分离视图逻辑和模板关系的正确方式。此外，视图逻辑通常比较复杂，所以一般使用模板引擎去描述当视图层变得比较笨重的时候。
. 我们找到了一个最好的解决方法去解决生成HTML和组件化树形目录从JavaScript代码中，这样你就可以使用任何编程语言去编写健壮的UI层
. 为了让这个问题简单化，我们增加了一个非常简单的，可选的类HTML语法的去创建React树形节点
. JSX使用HTML的语法去构建JavaScript对象。在React里使用纯JavaScript去创建一个链接你会这样写
    React.createElement('a', {href: 'https://facebook.github.io/react/'}, 'Hello!')
而使用JSX语法则变成:
    <a href="https://facebook.github.io/react/">Hello!</a>
