## js中的循环语句，for， forEach， for in, for of
### 原生js编辑for
### js提供了遍历数组对象的方案forEach map
Array.forEach(function(value , index , array){ //value为遍历的当前元素，index为当前索引，array为正在操作的数组
  //do something
},thisArg)
相同点：都可以遍历到数组中的每一个元素，参数相同，（回调函数，执行时的this值）
不同点：forEach影星原数组，返回值为undedind（执行回调结果之后，不论是否由return语句都是返回undefined
        map不应影响原素组，每一项都会对返回，如果没有return到某一项，则返回的当前项为null，得到一个新的数组
注：其他常用的数组遍历方法有：
    改变原数组：
        unshift：向数组开头插入某元素，返回数组长度
        shift：删除数组开头第一个元素，并返回删除元素，空即为undefined
        pop：删除数组结尾最后一个元素，并返回删除元素
        push：向数组最后插入一个元素，并返回数组长度
        reverse：颠倒数组顺序
        sort：对数组进行排序
        spilce：splice(start,length,item)删，增，替换数组元素，返回被删除数组，无删除则不返回

    不改变原数组：
    concat：连接多个数组，返回新数组
    join：将数组中所有元素以参数作为分割符，拼接成一个字符串
    slice：slice（start，end）返回选定元素
    map，filter，some（判断是否至少有一个元素满足测试条件，返回布尔值），every（判断数组中是否每个元素都能满足测试条件，返回一个布尔值），等不改变原数组
### for in / for of
    for in 以任意顺序遍历一个对象的可枚举属性，对于每个不同的属性，语句都会被执行，每次迭代时，分配的是属性名
    ES6新增了 遍历器(Iterator)机制，为不同的数据结构提供统一的访问机制。只要部署了Iterator的数据结构都可以使用 for ··· of ··· 完成遍历操作  ( Iterator详解 ：  http://es6.ruanyifeng.com/#docs/iterator )，每次迭代分配的是 属性值----普通对象不能使用for of进行遍历
    for...in循环会遍历一个object所有的可枚举属性。

　　for...of会遍历具有iterator接口的数据结构

　  for...in 遍历（当前对象及其原型上的）每一个属性名称（可枚举属性， 注意数组用for，in遍历的时候拿到是是索引而不是值）,而 for...of遍历（当前对象上的）每一个属性值


详解：https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for...of