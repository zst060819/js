# 第三天

## 数据类型

### 基本数据类型

- 在JS中一共有5种常用的基本数据类型：

  - 数值（Number）

    - 在JS中所有的数字（整数和浮点数）都属于数值类型

    - 例子：

      - 123
      - 3.1415926
      - ±Infinity （无穷）
      - NaN（Not a Number）非数字

    - 使用typeof去检查一个数值时会返回 "number"

    - 在JS中，能保证大部分的整数计算能得到一个精确的结果，小数计算时可能会得到一个近似结果，所以如果对于计算的精度要求过高（尤其涉及到钱了）千万不要在这算。

    - 其他进制的数值：

      - 二进制：0b 开头
      - 八进制：0o开头
      - 十六进制：0x开头

    - 数字可以使用分隔符来表示

      - ```javascript
        var a = 123_456_789;
        ```

    - 类型转换，其他的数据类型转换为Number

      - 显式类型转换（强制类型转换）

        1. Number()

           ```javascript
           var a = '10';
           a = Number(a);
           ```

        2. parseInt()（对付字符串）

           - 用来将一个字符串转换为一个整数

        3. parseFloat() (对付字符串)

           - 用来将一个字符串转换为一个小数
           - 原理：对字符串自左向右解析，获取所有的合法的数字

      - 隐式类型转换（自动类型转换）(❤)

        - 使用一元的+（原理和Number()一样，使用起来更加简单）

        - ```javascript
          var a = '10';
          a = +a;
          ```

      - 类型转换的情况：

        - 字符串：
          - 字符串是一个合法的数字，则直接转换为对应的数字。
          - 字符串不是一个合法的数字，则转换NaN
          - 空串和空格串都会转换为0
        - 布尔值：
          - true 转换为 1
          - false 转换为 0
        - null 转换为 0
        - undefined 转换为 NaN

  - 字符串（String）

    - 在JS中字符串需要使用引号引起来

    - 使用typeof检查一个字符串，会返回"string"

    - 双引号或单引号都行，但是不要混着用

    - 相同的引号之间时不能嵌套的

    - 转义字符（\）：

      - \\'   表示 '
      - \\\"  表示 "
      - \\\\  表示 \\
      - \\t  表示 制表符  
      - \\n 表示 换行

    - 类型转换（其他类型转换为String）：

      - 显式类型转换（强制）

        - String()函数
        - toString()方法
          - 对于null和undefined来说，调用toString()会报错！

      - 隐式类型转换（自动）❤

        - 可以通过为任意值加一个空串的形式来将其转换为字符串

        - ```javascript
          var a = 10;
          a = a + "";
          ```

          

  - 布尔值（Boolean）
    - 布尔值主要用来进行逻辑判断
    - 使用typeof检查一个布尔值，会返回 "boolean"
    - 布尔值只有两个：
      - true，表示真
      - false，表示假
    - 类型转换：
      - 显式
        - 使用Boolean()函数
      - 隐式 ❤
        - 为一个值进行两次取反，即可将其转换为布尔值
        - ```javascript
             var a = 10;
             a = !!a; 
          ```
    - 类型转换的情况 ❤：
      - 会被转换为false的情况：
        - null
        - undefined
        - 0
        - NaN
        - 空串
  - 空值（Null）
    - 空值用来表示空的对象
    - 只有一个值 null
    - 使用typeof 检查一个null时，会返回 "object"
  - 未定义（Undefined）
    - 未定义用来表示声明了却没有赋值的变量
    - 只有一个值 undefined
    - 使用typeof检查一个undefined时，会返回 "undefined"

## 运算符（操作符 operator）

-  通过运算符可以对一个或多个值进行运算或操作

### 算术运算符

- \+ 加法运算
- \- 减法运算 
- \* 乘法运算
- / 除法运算
- % 取模运算（两个数相除，取余数）
- ** 幂运算（求一个数的几次方）
- 注意：
  - 除了字符串的加法，所有的非Number类型的值进行算术运算时，都会先转换为Number然后再运算。
  - 任何值和NaN做运算结果都是NaN（除了字符串加法）
  - 两个字符串相加时，会自动将两个字符串连接为一个字符串，即所谓的拼串。
  - 任意值和字符串做加法时，都会转换为字符串然后在进行拼串操作。

### 一元运算符

- 一元运算符指只有一个操作数的运算符
  - 一元的+
    - 正号，它不会对数值产生任何影响，但是它会将非数值转换为数值
  - 一元的-
    - 负号，它会对数值进行符号位取反，正变负，负变正，同样也会将非数值转换为数值

## 作业

- 整理今天的内容
- 预习：
  - 运算符（比较、相等、逻辑、自增自减、条件、赋值）