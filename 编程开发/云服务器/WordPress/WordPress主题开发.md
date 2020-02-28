# WordPress主题开发

## 一、术语解释

- **Template（模板**） — 其实就是一个代码集，主题中很多地方会利用到这个代码集，所以把它们整合成一个模板，这样就就不必一遍遍输入这些重复代码。
- **Template file（模板文件**） — 一个包含一个或者多个代码集（模板）文件。每个主题是由多个模板文件组成的，比如：index.php，style.css，sidebar.php 等等。
- **Theme（主题**）或者 **WordPress theme（WordPress 主题）** — 所有你正在使用的文件：文本，图像，代码等等。注意： WordPress theme（主题）和 WordPress template(s)（模板）是两个不同的东西，尽管有些人认为他们一样。
- **Post（日志或者文章）** — 现在你读的就是一篇日志。此外，它是你 blog 的一个简单的条目，如：一个页面或者一篇日记。
- **Page（静态页面）** — 一种特殊的 post，它不是以分类组织的。它有别于你其他的日志。注意：在 WordPress，page（页面）和 Page（静态页面）是两种不同的东西。

## 二、主题层次结构

> WordPress主题文件存在优先级关系，以主页为例，home.php与index.php，WordPress依次查找这两个文件：
>
> - 如果存在home.php，则不管index.php是否存在，均使用home.php为博客首页模板；
> - 不存在home.php，则会查找index.php，存在则以index.php为博客首页模板，未找到则主题不会被识别。

### 主页

1. home.php
2. index.php

### 文章页面

1. single-{post_type}.php - 如果文章类型是videos（即视频），WordPress就会去查找single-videos.php（WordPress 3.0及以上版本支持）
2. single.php
3. index.php

### 页面

1. 自定义模板 - 在WordPress后台创建页面的地方，右侧边栏可以选择页面的自定义模板
2. page-{slug}.php - 如果页面的缩略名是news，WordPress将会查找 page-news.php（WordPress 2.9及以上版本支持）
3. page-{id}.php - 如果页面ID是6，WordPress将会查找page-6.php
4. page.php
5. index.php

### 分类

1. category-{slug}.php - 如果分类的缩略名为news，WordPress将会查找category-news.php(WordPress 2.9及以上版本支持)
2. category-{id}.php -如果分类ID为6，WordPress将会查找category-6.php
3. category.php
4. archive.php
5. index.php

### 标签

1. tag-{slug}.php - 如果标签缩略名为sometag，WordPress将会查找tag-sometag.php
2. tag-{id}.php - 如果标签ID为6，WordPress将会查找tag-6.php（WordPress 2.9及以上版本支持）
3. tag.php
4. archive.php
5. index.php

### 作者

1. author-{nicename}.php - 如果作者的昵称为rami，WordPress将会查找author-rami.php（WordPress 3.0及以上版本支持）
2. author-{id}.php - 如果作者ID为6，WordPress将会查找author-6.php（WordPress 3.0及以上版本支持）
3. author.php
4. archive.php
5. index.php

### 日期页面

1. date.php
2. archive.php
3. index.php

### 搜索结果

1. search.php
2. index.php

### 404 (未找到)页面

1. 404.php
2. index.php

### 附件页面

1. MIME_type.php - 可以是任何MIME类型 (image.php, video.php, audio.php, application.php 或者其他).
2. attachment.php
3. single.php
4. index.php

## 主题制作

> 一个WordPress主题至少包含以下两个文件:style.css 和index.php。

