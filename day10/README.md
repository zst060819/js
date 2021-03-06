# 第十天

## 高阶函数

- 当一个函数的参数或者返回值也是一个函数时，那么这个函数就是一个高阶函数。

  - ```javascript
    function fn(callback){
    	callback();
    }
    
    function fn2(){
        function test(){}
        return test;
    }
    ```

- 把函数作为参数使用：

  - 函数在JS中属于一等对象，别的对象能做的事函数都能做。
  - 所以函数也可以作为参数来使用。
  - 将函数作为参数使用，主要目的是将代码传递到函数中。
  - 作为函数的参数，它由我们定义，但是不由我们调用，这种函数被称为回调函数（callback）。

## 箭头函数

- 箭头函数是函数创建的一种特殊方式

- 语法：

  - ```javascript
    ([参数列表])=>返回值
    ```

- 箭头函数语法简单，主要用于设置回调函数，一般不会使用它来创建普通函数

- 注意事项：

  - ```javascript
    (a, b)=> a + b // 标准语法
    
    a => a + 10 // 如果箭头函数只有一个形参，可以省略()
    
    () => 30 + 10 // 没有形参，()不能省略
    
    () => {   // 如果函数体比较复杂，可以使用代码块{}
        var a = 10;
        var b = 20;
        return a + b;
    }
    
    () => ({a:10, b:33}) // 如果返回值是一个对象字面量，字面量外部必须加()
    ```

- 箭头函数的this，不由它自己的调用方式决定。

- 箭头函数的this，由其外部作用域来决定，外部作用域中的this是啥，箭头函数中的this就是啥！

- this的情况（根据调用方式的不同）：

  - 以函数调用时，this是window
  - 以方法调用时，this是调用方法的对象
  - 以构造函数调用时，this是新对象
  - 箭头函数，this由外层作用域决定
  - 未完，待续……
    



## 数组（array）

- 数组的方法：

  - 类方法（通过构造函数对象来调用的方法）

    - Array.isArray()
      - 用来检查一个值（对象）是否是数组，是数组返回true，不是返回false

  - 实例方法（通过实例对象来调用）

    - push()
      - 向数组的末尾添加一个或多个元素，并返回数组新的长度
    - pop()
      - 删除并返回数组的最后一个元素
    - unshift()
      - 向数组的开头添加一个或多个元素，并返回新的长度
    - shift()
      - 删除并返回数组的第一个元素

    - concat()

      - 用来连接两个或多个数组
      - 该方法不会影响到原数组，而是返回一个新的数组

    - join()

      - 用来将数组中的所有元素拼接为一个字符串
      - 参数：
        - 第一个参数，字符串，该字符串会成为连接符来连接每一个元素
          - 如果不指定，默认使用,作为连接符
      - 不会影响原数组

    - slice()

      - 用来抽取数组中部分元素，生成新数组（不会影响到原来的数组）
      - 参数：
        - 第一个参数，抽取的起始位置索引（包含起始位置）
        - 第二个参数，抽取的结束位置索引（不包含结束位置）
        - 如果省略第二个参数，默认会抽取到最后
        - 索引可以是负值，负值表示倒数第几个

    - splice()

      - 用来删除、添加、替换数组中的元素（会影响到原来的数组）

      - 参数：

        - 第一个参数，删除的起始位置索引
        - 第二个参数，删除的数量
        - 第三个后的参数，要添加的元素

      - 返回值：

        - 返回的是被删除的元素

      - 例子：

        - 删除元素

          - ```javascript
            var result = arr.splice(2,3); // 从索引2开始，向后删除3个元素
            // result 接收到的是被删除的元素
            ```

        - 替换元素

          - ```javascript
            var result = arr.splice(2,3,xxx,yyy,zzz);
            ```

        - 在指定位置插入元素

          - ```javascript
            arr.splice(2, 0, xxx, yyy);
            ```

            

    - indexOf()

    - lastIndexOf()

      - 用来查询元素在数组中第一次出现的位置
      - 参数：
        - 第一个，被查询的元素
        - 第二个，查询的起始位置（默认 0）
      - 返回值：
        - 找到元素，则返回元素第一次出现的索引
        - 没有找到，则返回-1
      - 区别：
        - indexOf() 从前往后找
        - lastIndexOf() 从后往前找

    - forEach()

      - 为数组中的每一个元素调用函数
      - forEach()需要一个回调函数作为参数，回调函数会调用多次（数组中有几个元素就调用几次），每次调用时，会将元素的信息作为参数传递进回调函数
      - 三个参数：
        - value 当前的元素
        - index 当前元素的索引
        - array 当前被遍历的数组

