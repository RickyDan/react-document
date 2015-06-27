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
