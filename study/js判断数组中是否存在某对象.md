# js判断对象数组中是否存在某个对象
参考：https://www.cnblogs.com/leiting/p/9253461.html
## 1、判断数组中是否存在某元素
    直接使用数组的indexOf方法，有返回当前索引，无返回-1
    var arr = [1.2.3]
    arr.indexOf(3)
## 2、通过遍历，判断对象标志性属性是否存在，
    定义flag表示，表明改元素是否存在，或变量来接找到的元素
    var flag = false
    var targetObject = null
    arr.forEach(item => {
        if(item.name === '张三'){
            alert('找到元素'， item)
            flag = true
            targetObject = item
        }
    })
## 3、判断数组中是否存在某元素，进行删除或添加操作
    利用string的indexOf方法
    var option={name: 'lisi'}
    if((JSON.stringify(arr).indexOf(JSON.stringify(option))==-1){
        <!-- 执行动态操作-->
    }
    注意：此方法，只能在对象内属性顺序一致的情况下才能判断准确，目标对象内属性与数组中对象属性顺序不一致，查找不到
    注意：返回某个指定的字符串在数组中首次出现的位置，如果要查找最后出现的位置，使用lastIndexOf() 
## 4、利用数组api some （数组中至少选在一个元素满足条件）返回布尔值
    arr.some(item => item.name === 'lisi')
## 5、find() 找到第一个符合条件的数组元素
    找到第一个满足条件的元素，返回该元素，并且不再遍历之后的元素，否则返回undefined，
    注意：find()对空数组，函数不执行，find不影响原数组
    arr.find(item => item.name === 'lisi')
## 6、 findIndex() 
    此方案与find类似，但它返回的是符合条件元素的索引，无满足条件元素则返回-1，其他注意事项与find相同



