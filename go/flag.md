#### flag 包：命令行参数解析工具

* 命令行参数：运行程序提供的参数
* 已定义命令行参数：程序中通过 flag.Xxx 定义的参数
* 非 flag 命令行参数：

##### 定义flag：

* flag.Xxx()   Xxx可以是Int 或 String等；返回一个相应类型的指针

  ```go
  var ip = flag.Int("flagname", 1234, "help message for flagname")
  ```

* flag.XxxVar()  将 flag 绑定到一个变量上

  ```go
  var flagvar int
  flag.IntVar(&amp;flagvar, "flagname", 1234, "help message for flagname")
  ```

* 自定义flag，只要实现 flag.Value 接口（要求receiver是指针）

  ```go
  flag.Var(&amp;flagVal, "name", "help message for flagname")
  ```

##### 解析已定义的flag

* flag.Parse()

##### flag 语法

* -flag   只支持bool类型
* -flag=x 
* -flag x   只支持非bool类型


