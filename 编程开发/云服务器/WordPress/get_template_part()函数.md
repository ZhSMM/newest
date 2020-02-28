# get_template_part()函数

1. 写法：`<?php get_template_part($slug,$name)`

2. 参数：

   - $slug:(required)通用模板名；
   - $name:(optional)指定的模板名；

3. 用途：

   - 加载一个指定的模板到另一个模板里面，不同于包含header,sidebar,footer;
   - 使得一个主题使用子模板来实现代码段重用变得简单;
   - 用于在模板中包含指定的模板文件,只需用指定参数slug和name就可以包含文件{slug}-{name}.php,最重要的功能是如果没有这个文件就包含没有{name}的.php文件文件。

4. 加载顺序：

   ```
   // 使用子主题里面的loop.php;
   // 假设主题文件夹wp-content/themes下父主题是twentyten子主题twentytenchild,那么下面的代码:
   
   <?php get_template_part( 'loop', 'index' ); ?>
   
   //php 的require()函数将按下面优先级包含文件
   1. wp-content/themes/twentytenchild/loop-index.php
   2. wp-content/themes/twentytenchild/loop.php
   3. wp-content/themes/twentyten/loop-index.php
   4. wp-content/themes/twentyten/loop.php
   ```

   