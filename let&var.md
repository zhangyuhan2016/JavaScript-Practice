## let && var
 
    for (let i = 0;i<5;i++){
        let i = 'zzz'
        console.log(i)
    }
    
> 上述代码执行后会发生什么呢？

    (5) zzz    

> 把代码通过Babel转换后会变成这个样子 

    for (var i = 0;i<5;i++){
        var i = 'zzz'
        console.log(i)
    }
    
> 那么这次输出结果会是什么呢？
    
    zzz

> 哈，是不是和你想的不太一样？
    

> **这是为什么呢？**

    for (let i = 0;i<5;i++){ //for里的i
          {
            let i = 'zzz'  //块里的i
            console.log(i)
          }
    }
    console.log(i) // i is not defined    
let 的作用域是块,所以log(i)时,RHS查询i一直都是块里的i,
for里的i不会影响块里,块里也影响不到for里的i


      for (var i = 0;i<5;i++){
             var i = 'zzz'
             console.log(i)
      }
      console.log(i) // NaN
      
而var就不一样了,
 **for里的i和块里的i**
指向一个引用,所以当i = 'zzz'后,
再次进入 **for()** 时,执行 i++ 时,相当于发生了下面这些
    
    
    i = +'zzz' + 1
    Number('zzz') //NaN 
    i = NaN
    NaN < 5 //false
    
所以for() 也就到此结束,然后你就看到了,只打印一次~
    
    for (var i = 0;i<5;i++){
           var i = 10
           console.log(i) //10
    }
    console.log(i) // 11
    
> 这样,是不是看起来清晰不少...