### call
    当调用一个函数时，可以赋值一个不同的 this 对象。this 引用当前对象，即 call 方法的第一个参数
    
    let data = {
        name: 'test'
    }
    function test(){
        console.log(this.name)
    }
    test.call(data) // test
    
### apply
    语法与 call() 方法的语法几乎完全相同，唯一的区别在于，apply的第二个参数必须是一个包含多个参数的数组（或类数组对象）。apply的这个特性很重要，
    
    let data = {
        name: 'data-name',
        show(){
            console.log(this.name)
        }       
    }
    let nameBefore = data.show
    
    data.show = function(){
        console.log('做些羞羞得事')
        this.name = 'Xiu~~' + this.name
        nameBefore.apply(this,[123])
    }
    
    // 改变console颜色
    let test = window.console.log
    window.console.log = function(str){
        test.apply(this,['%c' + str,'color:red;font-size:2rem'])
    }
    
### bind
    bind()最简单的用法是创建一个函数，使这个函数不论怎么调用都有同样的this值。常见的错误就像上面的例子一样，将方法从对象中拿出来，然后调用，并且希望this指向原来的对象。如果不做特殊处理，一般会丢失原来的对象。使用bind()方法能够很漂亮的解决这个问题：
    
    function test(){
        console.log(this.name)
    }
    window.name = 'window-name'
    test() // window-name
    let start = test.bind({name:'start'})
    start() // start