## flutter_json_model_generator
一个批量生成Dart model的python脚本。


## 依赖
该项目是在quicktype基础上做的封装，使用python脚本来解析生成代码。有以下依赖：
1. [quicktype](https://quicktype.io/)
  ```bash
  npm install -g quicktype
  ```
2. python3


## 使用
定义一个特殊的json: `type.json`, 内容如下：
```json
//{"name": "Login", "page": "login.dart"}
{
  "account": "",
  "pwd": ""
}

//{"name": "LoginResp", "page": "login.dart"}
{
  "code": 0,
  "msg": ""
}

//{"name": "Test", "page": "test.dart"}
{
  "test": ""
}
```
这个json文件中包含多个完整json, 每个json都有一个特殊的注解，用来标记 model名称 以及 这个model放在哪个dart文件里。

接着，调用命令行生成代码：
```python
python type.py
```


## 注意
一般情况下，不建议修改生成的Dart model。
特殊情况需要改动生成的代码，可以在该model上方加上`//keep`标记，防止下次代码生成时被覆盖。
