# 附录：Markdown 语法汇总及风格指南。

本 Markdown 语法内容参考了来自：
- [Markdown 语法说明](https://www.markdownguide.org/) 的内容。
- [Github](https://docs.github.com/zh/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) 的 Markdown 格式语法。

本 Markdown 风格指南参考了来自：
- [Google](https://google.github.io/styleguide/docguide/style.html) 所列的风格规范。
- [CTF Wiki Team](https://github.com/ctf-wiki/) 的 Markdown 编写规范。


并在其基础上有自己的一些改动。

在适用性上，本程序将会添加

- 基于 [obsidian](https://obsidian.md/) 的格式。
- 对[插件 Admonition](https://github.com/javalent/admonitions) 的支持。

以及其它内容。

**注意：本说明的内容没有做通用性的强制要求，用户可以将这份文档复制于自己使用的 Markdown 处理器下进行阅读，并确定处理器允许的语法范围，基于自己的使用风格进行筛选。由于 Markdown 处理器种类繁多，恕本文不一一说明哪些主流处理器支持哪些语法**。由于此文档被分发至 Github 上，因此采用的语法尽可能地都是满足 Github 支持范围内的。

阅读须知：以下的三级标题包含三个部分：

- 标题及其对应的语法。

    该部分便于用户查找，对 Markdown 使用进行基础查找的工具。

- 该语法的示例和效果。

    该部分是对该语法的实例说明和渲染展示，以助于用户理解和检查是否被支持。

- 其他说明。

    包括对于这个语法的额外说明、编写与排版建议、其他可能的语法说明等。

    为了保证内容条理。文章会采用一些简写来避免不必要的重复及方便查找。一些缩略包括：

    - [R] 此语法推荐采用。(Recommended)
    - [NR] 此语法不推荐采用。(Not Recommended)
    - [NS] 此语法存在，但本程序不支持。(Not Supported)
    - [TA] 基于排版的建议。(Typographical Advice)

        这部分内容即针对文本排版的一些具体建议。

    - [SA] 基于语法的建议。(Syntax Advice)

        这部分内容针对语法、词法、标点符号等的使用给出的建议。

    - [RA] 基于渲染效果的建议。(Rendering Advice)

        这部分内容是对本程序的转换提出的建议。

    - [CA] 基于内容的建议。(Content Advice)

        这部分内容是针对具体的语法下文本内容的建议。

    - [CO] 一些有纠纷的地方。（controversy）

        这部分是针对一些存在争议的语法形式说明。

    针对语法层面的缩写包括：
    - [B] Markdown 基本语法。(Basic syntax)

        基本语法是 [John Gruder](https://daringfireball.net/projects/markdown/) 所设计的 Markdown 语法，是所有 Markdown 处理器所支持的语法。

        应当指出的是，按照 John Gruder, Markdown 的设计是为了简化 HTML 标签。因此本文也将可被基础的 HTML 实现的语法视为基本语法。如对 `<a></a>` 标签的使用。但除非必要，一般本文会将 `HTML` 视为 \[NR\] 标签。

        > Markdown is not a replacement for HTML, or even close to it. Its syntax is very small, corresponding only to a very small subset of HTML tags. The idea is not to create a syntax that makes it easier to insert HTML tags. In my opinion, HTML tags are already easy to insert. The idea for Markdown is to make it easy to read, write, and edit prose. HTML is a publishing format; Markdown is a writing format.
        >
        > For any markup that is not covered by Markdown’s syntax, you simply use HTML itself. There’s no need to preface it or delimit it to indicate that you’re switching from Markdown to HTML; you just use the tags.

    - [AD] Markdown 高级语法。(Advanced syntax)

        高级语法是 Markdown 扩展语法，原则上会被大部分 Markdown 处理器所支持。

    - [CU] Markdown 拓展语法。(Customed syntax)

        此类语法是某些特定的 Markdown 处理器所支持的语法。

        一般地，未被语法说明所涵盖的内容都会被归类为拓展语法。

## 索引

- [标题](#标题)
- [段落](#段落)
- [文本样式](#文本样式)
- [块引用](#块引用)
- [列表](#列表)
- [代码及代码块](#代码及代码块)
- [分割线](#分割线)
- [链接](#链接)
- [图片](#图片)
- [表格](#表格)
- [脚注](#脚注)
- [定义列表](#定义列表)
- [任务列表](#任务列表)
- [折叠块](#折叠块)
- [Admonition](#告诫admonition)
- [关系图](#关系图)


## 标题

### 语法
Markdown 创建标题语法是在文本强添加一至六个井号 (`#`) 完成。井号和单词或短语之间有一个 **半角空格** 分隔。这被称为 ATX 标题。

```markdown
[B/R]
# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题
```

其他的语法包括
```md
[B/NR]
这是一级标题
====

[B/NR]
这是二级标题
----

[B/NR]
<h1>这是一级标题</h1>
<h2>这是二级标题</h2>
<h3>这是三级标题</h3>
<h4>这是四级标题</h4>
<h5>这是五级标题</h5>
<h6>这是六级标题</h6>
```
也被称为 Setext 标题。

---

对于大型的 Markdown 文档而言，编写者可能会希望能够具有标题的索引，能够通过索引到达不同的位置。

一种方法是采用原始的 HTML </a> 标签。
```md
[B]
## 目录
- [第一章](#ch1)
    - [第一节](#1-1)
    - [第二节](#1-2)
- [第二章](#ch2)

## <a id="ch1">第一章</a>
### <a id="1-1">第一节</a>
### <a id="1-2">第二节</a>

## <a id="ch2">第二章</a>
```
这种方法仅要求每个 `id` 唯一且与锚文本对应即可。但有些处理器 **并不支持类似的索引**。

另一种方法依赖于处理器自动对标题分配 id，可以通过直接使用锚文本来进行链接。
```md
[CU]
## 目录
- [标题1](#这是一个标题)
- [标题2](#othertitle)
- [标题3](#this-is-english-title)
## 这是一个标题
一般地，一些编辑器会自动以标题内容分配标题的 ID. 可以直接进行使用。

### 这是标题 2{#othertitle}
Markdown 是支持标题的自定义 ID. 如上面的标题所示。

### This is English Title
如果标题中有空格而未指定新的 ID, 使用时需要将空格替换为短划线 `-`.
```
此方式有下列要求：
- 只能针对各级标题进行索引。
- 对应的锚标签是标题的文本内容，空格由短划线 `-` 代替，锚标签名称全为小写(但对标题不做限制要求)。

### 书写建议
- [SA] 推荐使用 ATX 规范，尽管其允许标题之后跟 `#` 作为收尾(且数量不限)，但为了表示简便而一般不使用。

    **例外**：如果这份 Markdown 文档有在控制台进行查看的需要，可以考虑使用 Setext 规范以强调标题的层次关系。

- [SA] 尽管有处理器允许不加空格的处理方式，但这种方式可能会和 `tag` 进行冲突，因此仍然推荐使用空格。
- [TA] 绝大多数情况下，一级标题有仅应当有一个。标题的内嵌应当循序渐进，如二级标题下不能直接使用四级标题。混乱的嵌套方式会直接打乱大纲效果。
- [TA] 不推荐使用超过四级的标题。转换为 latex 时无法进行有效转换，除非模板中额外有针对五级标题和六级标题的定义。
- [TA] 不推荐在标题中使用其他内联符号，如加粗、斜体、下划线、MathJax 语法等。
- [CA] 一般而言，标题要求间接、明了，能够总结标题下所有段落的内容。 

## 段落
### 语法
段落是 Markdown 基本的结构，由一个或多个连续的文本行组成，段落之间以一个空行分隔。
```md
[B/R]
这是一个段落。
尽管在文本中添加了换行符，这个段落还是只包含一个段落。

这是第二段。\
通过增加反斜线，可以实现非空行的换行。

[B/NR]
这是一个段落。
在部分处理器中，不需要额外的空行也会将文本处理为段落。这是第二段。
这是第三段。
```

---

部分 Markdown 处理器支持使用 [MathJax 引擎](https://www.mathjax.org/) 渲染数学公式。就目前来说，绝大多数的处理器都是支持渲染公式的。数学公式分为行内公式和行间公式两种。行内公式由单独的 `$` 包围数学符号进行渲染，行间公式由单独的 `$$` 包围数学符号进行渲染。
```md
[CU/R]
给定半径 $r$, 圆的面积可以表示为 $S = \pi r^2$.

牛顿-莱布尼茨公式指出：
$$
\left. \int_a^b f(x) \mathrm dx = F(b) - F(a) = F(x) \right|_a^b
$$
其中 $F(x)$ 是 $f(x)$ 的原函数，或 $F'(x) = f(x)$
```
对于不熟悉数学公式的读者而言，请参考。

---

除去普通文本和数学公式外， Markdown 也对 emoji 具有一定程度的支持。推荐的做法是从 [Emojipedia](https://emojipedia.org/) 中直接将对应的 emoji 复制进文本。
```md
[AD/R]
今天是一个好天气 😊
```
对于部分 Markdown 处理器而言，也可以通过使用表情符号简码来进行插入。
```md
[CU/R]
今天是一个好天气 :blush:
```
请参考 [Markdown 文档示例](./md-example.md) 最后一部分查看可用的 emoji 简码。

### 书写建议

- [SA] 严格意义上而言，Markdown 的换行可以通过在文本行末尾添加两个或以上的空格、并进行换行实现。但是不能排除部分处理器在处理时会自动忽略行末空格的情况，因此，就一般性而言，更推荐使用空行或尾划线 `\` 进行换行。
- [SA] 早期的计算机会追求每行字符上限的效果。从早期的 72 字符、80 字符到 120 字符不等。如果有控制台上阅读的需求，而控制台不会进行自动换行，则会产生阅读不全的问题。因此通过换行不断行，可以实现一段长语句的阅读。现在的主流阅读器都应当有自动换行功能、宽屏显示器等，因此只是可以选择性地控制每行的字符数量。
- [SA] `$` 与公式之间不要留有空格，这会导致部分处理器将 `$` 解释为单独符号。尽管本人更推荐行内公式如示例所写(具有很强的阅读性)，但部分处理器会拒绝解析这种格式的行间公式(如 Github)。或者说，例中行间公式前后的回车是不必要的，可读性和渲染通用性由读者取舍。
- [TA] 中英文混合排版时，中文和英文之间应当留有一个半角空格、中文与数字之间应当有一个半角空格、数字与单位之间应当有一个半角空格。


## 文本样式
文本样式包括粗体[B]、斜体[B]、删除线[AD]、高亮[AD]、下标[AD]、上标[AD] 以实现强调效果。

### 语法
- 使用 `**` 或 `__` 包围文字实现加粗效果.
- 使用 `*` 或 `_` 包围文字实现斜体效果.
- 使用 `~~` 包围文字实现删除线效果.
- 使用 `==` 包围文字实现高亮效果.
- 使用 `~` 包围文字实现下标效果.
- 使用 `^` 包围文字实现上标效果.

```md
[B/R]
有两种不同的加粗方式，即 **A** 和 __B__. 

有两种不同的斜体形式，即 *A* 和 _B_.

[AD/R]
可以使用删除线来 ~~删除~~ 自己想划去的内容。

可以使用等号来 ==高亮== 自己希望高亮的内容。

H~2~O 中的 H 原子有三种同位素，其中 ^2^H 具有两个质子。
```

其他的语法包括：
```md
[B/NR]
这是 <strong>加粗</strong>，这是 <em>斜体</em>，这是<mark>高亮</mark>，这是 <del>删除线</del>，这是 <sub>下标</sub>，这是 <sup>上标</sup>。
```

### 书写建议
- [SA] 不推荐使用 下标、上标的文本样式，因为对阅读没有意义。一定要使用请使用 `HTML` 标签完成，部分处理器会把 `~[]~` 等同于 `~~[]~~` 而使下标失效，而且大多数的处理器貌似并不支持上下标的简便写法。
- [TA] 不推荐混合使用加粗、斜体、高亮等，繁杂的风格会降低阅读体验。
- [CA] 强调的内容应当是值得强调的，不要过多的使用加粗或进行全文强调。
- [CO] 对于加粗部分前后是否应该有半角空格存在争议，是否使用空格对最终的渲染效果也有影响，但是一般推荐添加空格，以防止部分渲染器渲染错误。


## 块引用
### 语法
块引用是对内容的一种引用方式，引用包括多个段落的块引用、嵌套的块引用等。
```md
[B/R/NS]
> 这是一段引用。

> 这是多段段落引用的第一段。
> 
> 这是多段段落引用的第二段。

> 这是一个可以嵌套的引用
>
>> 嵌套引用。
```

### 书写建议
- [NS] latex 原生生态不支持块引用，如果希望实现块引用，应当自行对 latex 模板进行设计。


## 列表
列表分为有序列表和无序列表。
### 语法
无序列表的创建需要在每个列表项前添加破折号 `-` 、星号 `*` 、加号 `+`。有序列表只需要对前项增加数字并紧跟半角的英文句点即可。
```md
[B/R]
- 第一项无序列表
- 第二项无序列表

    - 开始嵌套。

        > 无序列表中嵌套引用块。

    - 结束嵌套。

- 第三项无序列表。

---

+ 以加号开始的无序列表。
+ 无序列表二。

---

* 以星号开始的无序列表。
* 无序列表第二项。

---

1. 这是第一个有序列表项。
2. 这是第二个有序列表项。

    如果希望保留列表一致性的同时添加另外的元素，应当将此元素缩进四个空格 **而非一个制表符**。
    1. 有序列表可以嵌套。

        嵌套下的嵌套应当类推的进行缩进。
    
    2. 有序列表的嵌套结束。

    > 可以尝试嵌入引用块等。

3. 有序列表的结束。
```

其他的语法包括：
```md
[B/NR]
<ul>
<li> 这是列表一。</li>
<li> 这是列表二。</li>
</ul>

[B/NR]
1) 第一个有序列表项。
2) 第二个有序列表项。

[B/NR]
<ol>
<li>第一个有序列表项。</li>
<li>第一个有序列表项。</li>
</ol>
```

### 书写建议

- [SA] 有序列表并不要求数字连续。对于较多的项数，可以考虑懒惰计数(Lazy numbering). 但对于较少的项数，仍然推荐连续数字以便于阅读。
- [SA] **极力避免过多的嵌套**。具体的，对于 Markdown 不建议进行超过两层的嵌套——部分的处理器只能处理到两层。如果希望转换为 Latex, 也最多只能有四层的嵌套。
- [TA] 如果需要使用嵌套列表，部分规范会推荐采用四空格对齐。确切而言，在有序列表后使用两个空格，在无序列表符号后使用三个空格，以使列表内容和嵌入内容对齐。

    ```md
    [CO]
    1.  在有序列表之后使用两个空格。
        
        在书写嵌套文本时，文本就会与项目正文对齐。

    2.  继续使用两个空格。
    12. 重点在于文本上的对齐，如该项使用了一个空格。

    -   在无序列表后使用三个空格实现。

        同理，嵌套文本与项目正文对齐。

        1.  互相进行嵌套。

            八个空格对于嵌套下的嵌套。

        2.  这种方式被认为是更加整齐的。

    -   嵌套列表结束。
    ```

- [TA] 一般地，列表如果进行嵌套，那么内级的部分上下应当有一个空行。同
- [TA/CO] 部分风格会推荐使用统一的无序列表符号，即仅使用 `-` `+` `*` 其中之一，而非混合使用。另外一些风格会推荐使用多种符号以区分不同的有序列表。但无论如何，不应当在同一个列表中混用多种符号。

## 代码及代码块

### 语法
代码语法是将单词或短语表示为代码。行内的代码使用反引号 `` ` `` 进行包裹。
```md
[B/R]
这段代码由 `markdown` 完成。
```

代码块则使用围栏式代码块。通过在代码块前后添加不少于三个的对应反引号 (`` ` ``) 或波浪线 `~` 实现。
`````md
[AD/R]
```python
print("hello,world")
```

[AD/R]
~~~python
print("hello,world")
~~~

[AD/R]
````python
print("hello,world")
````
`````

其他的语法包括：
```md
[B/NR]
这是一段<code>代码</code>。

[AD/NR]
    也可以通过直接缩进四个空格或一个制表符来表示代码块，在此情况下，等同于不为围栏式代码块指定语言或指定为 `plaintext`.
```

### 书写建议
- [SA] 围栏式代码块可以由多于两个的 `` ` `` 包裹，并进而实现对代码块的一个文本嵌套，应当注意首尾的`` ` `` 数量应当一致。 行内可以通过 `` \` `` 进行转义。在行内代码块中，可以用两个 `` ` `` 进行包裹。
- [TA] 对围栏式代码块的最佳实践是尽可能指定语言，大多数处理器可以依据语言进行语法高亮。Markdown 支持的语言可以查询。当然，对于单行的代码块，采用四空格缩进会更加简洁。
- [CA] 尽可能避免代码内的不必要换行(如 Shell 的过长指令)，最好的做法是在不得不换行的地方加入反划线 `\` 以保证可以直接复制并使用。

    ````md
    ```shell
    bazel run :target -- --flag --foo=longlonglonglonglongvalue \
    --bar=anotherlonglonglonglonglonglonglonglonglonglongvalue
    ```
    ````


## 分割线

### 语法
创建分割线是在单独一行上使用三个或多个星号、破折号、下划线，且不包含其他任何内容。
```md
[R]

***

---

___

```

其他的语法包括：
```md
[B/NR]
<hr/>
```

### 书写建议
- [TA] 为了防止在有些渲染器上和二级标题混淆，请在分割线前后添加空白行。


## 链接 
### 语法
链接分为内链接、参考式链接、自动连接三类。

- 内链接的语法为 `[超链接显示名] (超链接地址) "显示 title"`。
- 参考链接被分为两部分：定义及其使用。

    - 定义部分用于设置属性。可以被放于任何位置，一般被放在使用部分段落之后或文档结尾。
    - 使用部分的语法为 `[超链接显示名][超链接 id]`，两个中括号之间可以具有单个半角空格。

    定义部分的语法包括：
    - `[超链接 id]: 超链接地址`
    - `[超链接 id]: 超链接地址 "显示 title"`
    - `[超链接 id]: 超链接地址 '显示 title'`
    - `[超链接 id]: 超链接地址 (显示 title)`
    - `[超链接 id]: <超链接地址> "显示 title"`
    - `[超链接 id]: <超链接地址> '显示 title'`
    - `[超链接 id]: <超链接地址> (显示 title)`

- 自动链接会直接插入超链接，其语法为 `<超链接地址>`。
```md
[B/R]
请参考 [此文本](https://markdown.com.cn/basic-syntax/links.html "暂时的链接标题")

如有问题，可以联系 [该邮箱](mailto:123@example.com "我的邮箱")。

请参考 [此文本][md-link]。

[md-link]: https://markdown.com.cn/basic-syntax/links.html "暂时的链接标题2"

这部分的参考来源于 <https://markdown.com.cn/basic-syntax/links.html>
```

其他的语法包括
```md
[B/NR]
请参考<a href="https://markdown.com.cn/basic-syntax/links.html" title="暂时的链接标题">此文本</a>
```

### 书写建议
- [SA] 如果希望实现文本内链接，请采用 `<a id="">` 命令和锚文本实现。
- [CA] 一般的，超链接文本应当尽可能短而富有信息。不推荐采用 “此链接” 或 “点击此处” 这样的文本，而是说明链接指向的内容或总结。


## 图片
### 语法
markdown 对于图片的添加格式为 `![图片 alt](图片链接 "图片标题")`
如
```md
[B/R]
![这是一张图片](https://www.runoob.com/images/pulpit.jpg  "图片标题")

[B/R]
[ ![这是一张图片](https://www.example.com/image.jpg "图片标题") ](www.example.com)
```

### 书写建议

- [SA] 图片链接支持绝对路径、相对路径和网络地址。
- [CA] Markdown 支持多种图片格式，包括 PNG、JPEG、GIF[NS] 和 SVG 等。
- [CA] 原生的 Markdown 不支持设置图片对齐方式和图片缩放，如有需要，推荐使用 HTML 完成。

    ```md
    <img src="图片链接" alt="图片 alt" title="图片 title" width="图片宽度" height="图片高度" align="left/center/right" />
    ```

- [CA] 图片的描述应当能够总结图片，因为图片描述能够作为图片加载失败时的替代文本。



## 表格
### 语法
在 Markdown 中添加表，使用不少于三个的连字符 `---` 以创建每列的标题(表头)，并用管道符 `|` 进行每列的分隔。可以通过在连字符的左侧、右侧或两侧添加 `:` 以进行左对齐、右对齐或居中对齐。
```md
[AD/R]
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
```


### 书写建议
手动使用连字符或管道创建表可能很麻烦，可以尝试使用 Markdown 表格生成器：<https://www.tablesgenerator.com/markdown_tables> 或 <https://tableconvert.com/zh-cn/markdown-generator>  来自动生成 Markdown 格式的文本。

- [SA] 表格中可以添加链接、代码(而非代码块)、加粗、斜体等强调。但不能在其中添加标题、块引用、列表、水平线、图像等。
- [TA] 通过字符代码 `&#124;` 或反转义 `\|` 以在表中显示竖线 `|` 字符。
- [CA] Markdown 中的任何表格都应当是小的。大而复杂的表格不利于直接阅读和修改，对于大而复杂的表格可以考虑采用列表等价实现。



## 脚注
### 语法
脚注是用来进行注释和参考的，支持 Markdown 脚注的编辑器一般会对脚注进行超链接设置。读者可以单击以互相跳转。
```md
[AD/R]
这里将添加一个脚注[^1]， 脚注可以插入符号或数字[^foot]。

[^1]: 脚注不能放在列表、块引用和表内。
[^foot]: 可以看到，采用符号也同样可以进行脚注标记。
```

### 书写建议


## 定义列表

### 语法
**定义列表** 由术语和定义组成，术语和定义之间用冒号分隔。对于支持这个定义的处理器而言，其需要在第一行键入术语、另起一行键入一个冒号，后跟一个空格和定义。
```md
[AD/R/NS]
首项
: 首项的定义是最开始的项。

尾项
: 尾项的定义是最后的项。
: 尾项的第二定义为，从后往前进行计数的第一个项。
```

其他的语法包括：
```md
[B/R]
<dl>
    <dt>首项</dt>
    <dd>首项的定义是最开始的项。</dd>
    <dt>尾项</dt>
    <dd>尾项的定义是最后的项。</dd>
    <dd>尾项的第二定义为，从后往前进行计数的第一个项。</dd>
</dl>
```

### 书写建议


## 任务列表

## 语法

任务语法列表可以创建带有复选框的项目列表。
```md
[AD/R/NS]
- [x] 此工作已完成。
- [ ] 工作一：提示用户，复选框中括号内包含一个空格。
- [ ] 工作二：提示用户，复选框可以包含多种类型。
```
### 书写建议

## 折叠块

### 语法
折叠块是纯粹的 HTML 语法内容。
````md
<details>

<summary>这是折叠块折叠后显示的内容</summary>

#### 四级标题
折叠块允许进行大多数 Markdown 内容的书写。
```python
print("hello,world")
```
</details>
````

### 书写建议


## 告诫(Admonition)

## 关系图
