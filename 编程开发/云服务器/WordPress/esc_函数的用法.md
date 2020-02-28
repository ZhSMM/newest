# esc_函数的用法

> WordPress中esc_函数主要有esc_js()、esc_url() 、esc_html()、 esc_sql()、 esc_attr()，用来对相应的语句进行过滤。

## esc_js()

1. 写法：esc_js($text);
2. 参数：
   - $text:(string)(required)要过滤的字符串；
3. 返回值：过滤后的字符串；
4. 用途：esc_js() 用来转义引号,加上反斜线,一般用来过滤内嵌在 Html 中的 JS。

## esc_url()

1. 写法：esc_url( $url, $protocols, $_context );
2. 参数：
   - $url: (string) (required) 将要被清理过滤的 URL；
   - $protocols:(array) (optional) 可以接受协议的数组，如果没有设置，默认是：'http', 'https', 'ftp', 'ftps',  'mailto', 'news', 'irc', 'gopher', 'nntp', 'feed', 'telnet'；
   - $_context:(string) (optional) 如何返回 URL；
3. 返回值：(string) 已经清理过滤的URL。
4. 用途：用于URL过滤
   - 拒绝不是下面协议的 URL （defaulting to http, https, ftp, ftps, mailto, news, irc, gopher, nntp, feed, and telnet）；
   - 消除无效字符和删除危险字符；
   - 将字符转换成 HTML 实体，并且将 & 和 单引号（'） 转换成数字实体：&#038, &#039；
5. 开发者可以通过 cleaned_url 这个 filter 接口对返回 $url 进行再次过滤。

## esc_html

1. 写法：esc_html( $text );
2. 参数：
   - $text:(string)(required)要转义的字符串。
3. 返回值：(string)返回转义后的字符。
4. 用途：esc_html() 函数用来转义 Html 代码,让 Html 代码不转义。
5. 示例:`<?php esc_html('<a href="http://www.example.com"> A link</a>')`

## esc_sql

1. 写法：esc_sql( $data );
2. 参数：
   - $data:(string)(required)要转义的字符串。
3. 返回值：(string)返回转义后的字符串，可以直接添加到Sql语句。
4. 用途：esc_sql() 用来过滤准备添加到 Sql 语句里边的字符串，防止 Sql 注入和 Sql 语句被数据干扰出现异常。

## esc_attr

1. 写法：esc_attr($text);
2. 参数：
   - $data:(string)(required)要转义的字符串。
3. 返回值：(string)返回转义后的字符串。
4. 用途：对动态输出的属性值进行转义。