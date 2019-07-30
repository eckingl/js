## Bootstrap

+ **响应式布局**
  1. 同一套页面适应不同分辨率的设备
  2. 实现
     1. 依赖于栅格系统:将一行平均分成12个格子,可以指定元素占几个 
  3. 步骤
     1. 定义容器.相当于之前的table
        1. 容器分类
           1. container:固定宽度
           2. container-fluid:100%宽度
     2. 定义行,相当于之前的tr 样式 row
     3. 定义元素,指定该元素在不同设备上,所占格子数目 样式:col-设备代号-格子数目
        1. 设备代号
           1. xs:<768px  :  col-xs-12
           2. sm:>768px  :  col-sm-12
           3. md:>992px  :  col-md-12
           4. lg:>1200px  :  col-lg-12
  4. 注意
     1. 栅格类属性向上兼容,
     2. 真实设备小于设置栅格类属性的最小值,回一个元素占满一行
  
+ **CSS样式和JS插件**

  + 全局CSS设置

    1. 按钮:修改class,各种类型链接为https://v3.bootcss.com/css/#buttons

       1. ```html
          <input class="btn btn-default" type="submit"value="Submit">
          ```

    2. 图片:任意尺寸都占100% https://v3.bootcss.com/css/#images

       ```html
       <img src="..." class="img-responsive" alt="Responsive image">
       ```

    3. 表格

       ```html
       <table class="table table-bordered"></table>
       ```

    4. 表单

  + 组件

    1. 导航条
    2. 分页条

  + 插件

    1. 轮播图