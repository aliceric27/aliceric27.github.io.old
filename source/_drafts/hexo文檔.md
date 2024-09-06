---
title: hexo文檔
tags:
---

https://theme-next.iissnan.com/

[Hexo + NexT 的特殊標籤 | Miles' Blog (mileschou.me)](https://mileschou.me/blog/hexo-next-note-1/)
[](https://blog.cyida.com/2023/hexo-next-tags.html)
#### 使用方式

```html
{% note class_name %} Content (md partial supported) {% endnote %}
```

其中，`class_name` 可以是以下列表中的一个值：

{% raw %}{% endraw %}

{% note default %}內容{% endnote %}

{% note primary%}內容{% endnote %}

{% note success%}內容{% endnote %}

{% note info%}內容{% endnote %}

{% note warning%}內容{% endnote %}

{% note danger%}內容{% endnote %}

- `default`
- `primary`
- `success`
- `info`
- `warning`
- `danger`

#### 效果示例:

![image-20230220172419422](https://i.imgur.com/9LkC8J4.png)

## 文本居中的引用

此标签将生成一个带上下分割线的引用，同时引用内文本将自动居中。 文本居中时，多行文本若长度不等，视觉上会显得不对称，因此建议在引用单行文本的场景下使用。 例如作为文章开篇引用 或者 结束语之前的总结引用。

#### 使用方式

- HTML方式：使用这种方式时，给 `img` 添加属性 `class="blockquote-center"` 即可。
- 标签方式：使用 `centerquote` 或者 简写 `cq`。

此标签要求 NexT 的版本在 **0.4.5** 或以上。 若你正在使用的版本比较低，可以选择使用 `HTML` 方式。

 **标签调用方法**

```html
<!-- HTML方式: 直接在 Markdown 文件中编写 HTML 来调用 -->
<!-- 其中 class="blockquote-center" 是必须的 -->
<blockquote class="blockquote-center">blah blah blah</blockquote>

<!-- 标签 方式，要求版本在0.4.5或以上 -->
{% centerquote %}blah blah blah{% endcenterquote %}

<!-- 标签别名 -->
{% cq %} blah blah blah {% endcq %}
```


```
{% button #, Text %}
```

- url : Absolute or relative path to URL.
- text : Button text. Required if no icon specified.
- icon : Font Awesome icon name. Required if no text specified.
- [class] : Optional parameter. Font Awesome class(es): fa-fw | fa-lg | fa-2x | fa-3x | fa-4x | fa-5x
- [title] : Optional parameter. Tooltip at mouseover.

1. 文字标签按钮：

```
{% btn #, Text %}{% btn #, Text & Title,, Title %}
```

2. 图标按钮：

```
{% btn #,, home fa-5x %}
{% btn #,, home fa-4x %}
{% btn #,, home fa-3x %}
{% btn #,, home fa-2x %}
{% btn #,, home fa-lg %}
{% btn #,, home %}
```

3. 文字 & 图标按钮

```
{% btn #, Text & Icon (buggy), home %}
{% btn #, Text & Icon (fixed width), home fa-fw %}

```

```
{% btn #, Text & Large Icon, home fa-fw fa-lg %}
{% btn #, Text & Large Icon & Title, home fa-fw fa-lg, Title %}
```

4. 在文字中使用

```
Lorem {% btn #, Lorem, home fa-fw fa-lg %} ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident {% btn #, Ipsum, home fa-fw fa-lg %}, sunt in culpa qui officia deserunt mollit anim id est laborum.

```
5. 在其它标签中使用按钮

```
{% note info %}
{% btn #, Text & Icon, home fa-fw %}

{% btn #,, home, Title %}{% btn #, Text %}

[Link](#)
{% endnote %}

```
6. 按钮框设计

```
{% btn #,, heading %}{% btn #,, fab fa-edge %}{% btn #,, times %}{% btn #,, circle-notch %}
{% btn #,, italic %}{% btn #,, fab fa-scribd %}
{% btn #,, fab fa-google %}{% btn #,, fab fa-chrome %}{% btn #,, fab fa-opera %}{% btn #,, gem fa-rotate-270 %}

```
7. 按钮相对 URL 链接
```
<div class="text-center">{% btn #, Previous Chapter, arrow-left fa-fw fa-lg, Previous Chapter (Full Image) %} {% btn #, Next Chapter, arrow-right fa-fw fa-lg, Next Chapter (Label) %}</div>

```

8. 按钮绝对 URL 链接
```
<div class="text-center">{% btn https://github.com, GitHub, fab fa-github fa-fw fa-lg, GitHub %}</div>

```

四、Label 标注

```
Lorem {% label @ipsum %} {% label success@dolor sit %} amet, consectetur {% label success@adipiscing elit, %} sed {% label info@do eiusmod %} tempor incididunt ut labore et dolore magna aliqua.

Ut enim *{% label warning @ad %}* minim veniam, quis **{% label danger@nostrud %}** exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate ~~{% label default @velit %}~~ <mark>esse</mark> cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


```