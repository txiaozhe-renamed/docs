#### flag

##### 提供一系列解析命令行参数的功能接口

* 命令行语法（以下语法对一个或两个 '-' 效果是一样的）

  ```shell
  -flag // 只支持bool类型
  -flag=x 
  -flag x // 只支持非bool类型
  ```

  整型：支持10进制、16进制和负数等

  bool型支持：1，0，t，f，T，F，true，false，TRUE，FALSE，True，False

* 定义flag的方式

  * 通过`flag.String(),Bool(),Int()`等`flag.Xxx()`方法，这种方法返回一个相应的指针

    ```go
    import "flag"
    var ip = flag.Int("flagname", 1234, "help message for flagname")
    ```

  * 通过`flag.XxxVar()` 方法将flag绑定到一个变量

    ```go
    var flagvar int
    func init() {
      flag.IntVar(&flagvar, "flagname", 1234, "help message for flagname")
    }
    ```

  * 通过`flag.Var()`绑定自定义类型，自定义类型需实现Value接口（Receives必须为指针），如：

    ```go
    flag.Var(&flagVal, "name", "help message for flagname")
    ```

    对于这种类型的flag，默认值为该变量类型的初始值

* 调用`flag.Parse()` 解析命令行参数到定义的flag

  ```go
  flag.Parse()
  ```

  解析函数将在碰到第一个非flag命令行参数时停止，非flag命令行参数是指不满足命令行语法的参数，如命令行参数为`cmd -flag=true abc`，则第一个非flag命令行参数为`abc`

* 调用Parse解析后，就可以直接使用flag本身（指针类型）或者绑定的变量值

  ```go
  fmt.Println("ip has value ", *ip)
  fmt.Println("flagvar has value ", flagvar)
  ```

  还可通过`flag.Args()`，`flag.Arg(i)` 来获取flag命令行参数