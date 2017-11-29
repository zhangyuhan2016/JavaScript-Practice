## 不定时更新的笔记

## CSS
  * ### 背景渐变
        background: linear-gradient(to bottom right, red , blue);
  * ### input placeholder颜色
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
  * ### input 光标颜色 
  
    * [caret-color](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color)
    * [webkit-text-fill-color](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-fill-color)
    ```css  
    
    /* 方法1 */
    input {
      caret-color: red;
    }
    /* 方法2 */
    input {
      color: red; /* color of caret */
      -webkit-text-fill-color: black;
    }
    ```
  * ### input focus边框颜色
      * [outline](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)
      ```css
        input:focus{
          outline: 3px double rgba(76, 171, 145, 0.8);
        }
      ```       
  * ### 滚动条
    ```css
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
    ```
  * ### 点击背景闪动
        -webkit-tap-highlight-color:transparent; 背景透明        
  * ### 文本
         $ 大写
         
            text-transform: uppercase;
            
         $ 多行截断
         
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
            overflow: hidden;  
  * ### 鼠标样式 [cursor-api](https://developer.mozilla.org/zh-CN/docs/Web/CSS/cursor)

        curosr :url(1.png) x y,auto;
        
        pointer-events: none; //阻止事件冒泡
          
        (当使用pointer-events时curosr样式为默认样式)
        可以通过js阻止事件冒泡
        $(selector).on('click',function(e){
          e.preventDefault();
        })
        x,y可以调整坐标     
  * #### IE
         透明 filter:alpha(opacity=50);
         通过float居中  
## JS
   * #### jQuery
         input checked 设置后没有选中效果的解决  $(this).prop("checked",true)
           
         鼠标进入离开  $(selector).hover(f1,f2)
## Vue
   * #### keep-alive
   ```vue
    // routes 配置
    export default [
      {
        path: '/',
        name: 'home',
        component: Home,
        meta: {
          keepAlive: true // 需要被缓存
        }
      }, {
        path: '/:id',
        name: 'edit',
        component: Edit,
        meta: {
          keepAlive: false // 不需要被缓存
        }
      }
    ]
    // App.vue
    <keep-alive>
        <router-view v-if="$route.meta.keepAlive">
            <!-- 这里是会被缓存的视图组件，比如 Home！ -->
        </router-view>
    </keep-alive>
    
    <router-view v-if="!$route.meta.keepAlive">
        <!-- 这里是不被缓存的视图组件，比如 Edit！ -->
    </router-view>
   ```     
## [electron-vue](https://simulatedgreg.gitbooks.io/electron-vue/content/cn/)
   > 如果windows安装出现问题,请详细阅读[文档](https://simulatedgreg.gitbooks.io/electron-vue/content/en/getting_started.html#a-note-for-windows-users)
   > 按图索骥还是遇到了问题,请尝试使用cnpm
   > 如果还有问题请参看 [这里](https://github.com/SimulatedGREG/electron-vue/issues)
## Other
   * ### LHS & RHS
         赋值的目标（LHS）和 赋值的源（RHS）。

   * ### 野狗云
         // 查询指定节点
         ref = sync('users/chen');
         ref.set({name:'merry chen'});
            
         ref = sync('users');
         ref.update({'chen':{name:'merry chen'}});
   * ### [mockjs](https://github.com/nuysoft/Mock/wiki)
         // vue & axios & mock
         const Mock = require('mockjs');
         
         Mock.mock('http:xxx/test', {
           'name': '@name',
           'age|1-100': 100,
           'color': '@color'
         });
         
         axios.get('/test')
              .then(function (res) {
                 console.log(res);
              });
        
##  问题 
    Q: Uncaught SyntaxError: Invalid regular expression flags
    A: js拼写不符合规则,检查代码   
     
     
  
## 学习实践
   * [let & var 的区别](./let&var.md)
   * [call & apply & bind](./call&apply&bind.md)