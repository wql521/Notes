# 借助Flask框架生成python的API接口

## 例子

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
```

### 例子解释

1. 首先我们导入了 Flask 类。该类的实例将会成为我们的 WSGI 应用。
2. 接着我们创建一个该类的实例。第一个参数是应用模块或者包的名称。 `__name__` 是一个适用于大多数情况的快捷方式。有了这个参数， Flask 才能知道在哪里可以找到模板和静态文件等东西。
3. 然后我们使用 route() 装饰器来告诉 Flask 触发函数 的 URL 。
4. 函数返回需要在用户浏览器中显示的信息。默认的内容类型是 HTML ，因此字 符串中的 HTML 会被浏览器渲染。

定义接口访问路径及访问方式：@api.route(’/index’,methods=[‘get/post/PUT/DELETE’])
定义函数，注意需与路径的名称一致，设置返回类型并支持中文：def index(): return json.dumps(ren,ensure_ascii=False)
三种格式入参访问接口：
1 url格式入参：flask.request.args.get(‘id’)
2 form-data格式入参：pwd = flask.request.values.get(‘pwd’)
3 josn格式入参：pwd = flask.request.json.get(‘pwd’)