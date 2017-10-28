## 不定时更新的笔记
## LHS & RHS
    赋值的目标（LHS）和 赋值的源（RHS）。
## 渐变
    background: linear-gradient(to bottom right, red , blue);
## 野狗云
    ref = sync('users/chen');
    ref.set({name:'merry chen'});
    
    ref = sync('users');
    ref.update({'chen':{name:'merry chen'}});

<<<<<<< HEAD
##  问题 
    Q: 部分手机不执行js,折腾了半天发现是 'use strict'的原因
    A: "use strict" 单引号不解析？
    
    Q: Uncaught SyntaxError: Invalid regular expression flags
    A: js拼写不符合规则,检查代码   
## HTML5 改变input placeholder颜色
    ::-webkit-input-placeholder { /* WebKit browsers */
        color:    #999;
    }
    :-moz-placeholder { /* Mozilla Firefox 4 to 18 */
        color:    #999;
    }
    ::-moz-placeholder { /* Mozilla Firefox 19+ */
        color:    #999;
    }
    :-ms-input-placeholder { /* Internet Explorer 10+ */
        color:    #999;
    }

## ipone4 兼容性
    需注意flex
## 点击背景闪动
     -webkit-tap-highlight-color:transparent; 背景透明
## jQuery
    input checked 设置后没有选中效果的解决  $(this).prop("checked",true)
    
    鼠标进入离开  $(selector).hover(f1,f2)
    
## IE
    透明 filter:alpha(opacity=50);
    通过float居中
## 文本
    # 大写
        text-transform: uppercase;
    # 多行截断
        display: -webkit-box;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
        overflow: hidden;
## 滚动条
        html,body {
            scrollbar-face-color: #d6def5; /*滚动条3D表面（ThreedFace）的颜色*/
            scrollbar-highlight-color:#fff; /*滚动条3D界面的亮边（ThreedHighlight）颜色*/
            scrollbar-shadow-color:#eeeeee; /*滚动条3D界面的暗边（ThreedShadow）颜色*/
            scrollbar-3dlight-color:#eeeeee; /*滚动条亮边框颜色*/
            scrollbar-arrow-color:#fff; /*滚动条方向箭头的颜色 */
            scrollbar-track-color:#fff; /*滚动条的拖动区域(TrackBar)颜色*/
            scrollbar-darkshadow-color:#fff; /*滚动条暗边框（ThreedDarkShadow）颜色*/
        }
        ::-webkit-scrollbar{
            width: 0;
        }
## canvas 
    test

## 移动端事件
    touchstart:     //手指放到屏幕上时触发
    
    touchmove:      //手指在屏幕上滑动式触发
    
    touchend:    //手指离开屏幕时触发
    
    touchcancel:     //系统取消touch事件的时候触发，这个好像比较少用

## cursor 自定义鼠标样式    
       curosr :url(1.png) x y,auto;
        
       pointer-events: none; //阻止事件冒泡
       
       禁止事件的时候怎么显示curosr
            —— 正常使用 curosr 事件冒泡通过js控制
            $('.forbidden').on('click',function(e){
              e.preventDefault();
            })
    x,y可以调整坐标
   [cursor-api](https://developer.mozilla.org/zh-CN/docs/Web/CSS/cursor)
   
## 学习记录
   * <a herf="./let & var.md">let & var</a>
=======
<a href="./let & var.md">let & var</a>
>>>>>>> origin/master
