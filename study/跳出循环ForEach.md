## forEach
### return false 终
作用：只终止本次继续执行（即本次循环return false之后的代码不执行），而不能终止for循环
### 正确终止forEach循环的方法：使用抛异常的方式实现终止
try{
    arr.forEach(item, index) => {
        if ( index !== 3) {
            throw Error();
          }
    }
} catch(e){console.log(e)}
## for
### break
使运行的语句推出包含在最内层的循环或者推出一个switch语句
### continue
使用continue结束本次循环
continue语句只能用在while语句、do/while语句、for语句、或者for/in语句的循环体内
