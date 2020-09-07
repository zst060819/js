# 第二十天

## 键盘事件

- keydown
  - 按键按下的事件
- keyup
  - 按键松开的事件
- 注意：
  - 键盘事件只能被可以获取焦点的元素触发，键盘事件通过会绑定给表单项、超链接、document
  - 键盘按下的事件，如果按着一个按键不松开，事件会被持续触发（第一次和第二次触发的间隔会比较长）
- 事件对象的属性：
  - key，显示当前按下的按键信息
  - ctrlKey 判断ctrl是否被按下
  - altKey 判断alt是否被按下
  - shiftKey 判断shift是被按下

## 定时器

- 延时调用

  - 使用setTimeout()来设置延时调用

  - 使用延时调用时，函数不会立即执行，而是在多长时间后被调用

  - 参数：

    - 被调用的函数
    - 间隔的时间（毫秒）

  - 返回值：

    - 返回一个唯一的id作为标识，可以通过该id来关闭延时调用
    - clearTimeout(id)
      - 用来关闭延时调用

  - 例子：

    - ```javascript
      setTimeout(function(){},3000)
      ```

- 定时调用

  - 使用setInterval()来设置函数的定时调用

  - 使用定时调用，函数将会被调用多次，并且每次执行都会间隔一定的时间

  - 它的用法和setTimeout()一样，不同点在于，setTimeout()只会调用一次函数，setInterval()会反复调用多次

  - 需要通过clearInterval()来关闭定时调用

    