# Markdown
`.markdownlint.json` 规则文件，放在项目目录下结合Vscode `markdownlint` 插件可以实时检测代码编写错误。

## 规则列表

### MD001-标题一次只能增加一个级别

### ~~MD002-第一个标头应为顶层标头(#)~~
> 注意：MD002已被弃用，默认情况下处于禁用状态。 [MD041/第一行标题](#MD041-文件中的第一行应为顶层标题)提供了改进的实现。

### MD003-标题样式
**params**: `style` ("consistent", "atx", "atx_closed", "setext", "setext_with_atx", "setext_with_atx_closed"; default "consistent");

``` markdown
"consistent": 默认，标题格式要一直
# ATX style H1

## ATX style H2

"atx"
# ATX style H1

"atx_closed"

# Closed ATX style H1 #

"setext"
Setext style H1
===============

Setext style H2
---------------

"setext_with_atx" 和 "setext_with_atx_closed" setext 和 atx 混用

"setext_with_atx"
Setext style H1
===============

Setext style H2
---------------

### ATX style H3

"setext_with_atx_closed"

Setext style H1
===============

Setext style H2
---------------

### ATX style H3 ###
```

### MD004-无序列表样式
**params**: `style` ("consistent", "asterisk", "plus", "dash", "sublist"; default "consistent")

- `consistent`: 默认，列表符号要统一
- `asterisk`: * 号
- `plus`: + 号
- `dash`: - 号
- `sublist`: 每个子列表具有与其父列表不同的一致符号

### MD005-同一级别列表缩进不一致 默认开启，关闭设置 `MD005: false`

### MD006-列表缩进从头开始

### MD007-无序列表缩进空格
**params**: `indent`(number; default 2)

### MD008-无

### MD009-行尾空格
**params**: `br_spaces, list_item_empty_lines` (number; default 2, boolean; default false)

- `br_spaces`: 注意：必须br_spaces将此参数设置为> = 2才能生效。设置br_spaces为1的行为与0相同，不允许任何尾随空格。
- `list_item_empty_lines`: 空格来缩进列表项内的空白行，但是某些解析器需要使用空格。将list_item_empty_lines参数设置true 为允许此操作

### MD010-包含硬制表符而不是使用空格缩进的任何行触发
**params**: `code_blocks` (boolean; default true)

### MD011-反向链接语法
使用 `(link)[https://www.example.com]` 报错

### MD012-多个连续的空白行
**params**: `maximum` (number; default 1)

### MD013-单行最大长度
**params**: `line_length, heading_line_length, code_block_line_length, code_blocks, tables, headings, headers` (number; default 80, boolean; default true)

### MD014-命令前使用美元符号而不显示输出

### MD015-无

### MD016-无

### MD017-无

### MD018-atx标题`#`号后没有空格 `#h1`

### MD019-atx标题`#`号后有多个空格 `#  h1`

### MD020-atx_closed标题(#)跟文字中间没有空格 `#h1#`

### MD021-atx_closed标题(#)跟文字中间有多个空格 `#  h1  #`

### MD022-标题上下空白行
**params**: `lines_above, lines_below` (number; default 1)

- `lines_above`: 标题上面
- `lines_below`: 标题下面

### MD023-标题必须从行首开始

### MD024-具有相同内容的多个标题
**params**: `siblings_only, allow_different_nesting` (boolean; default false)

如果将参数 `siblings_only` 或 `allow_different_nesting` 设置为true，则允许对非同级标题进行标题重复

### MD025-同一文档中的多个顶级标题

### MD026-标题中的标点符号
**params**: `punctuation` (string; default ".,;:!?。，；：！？"), `punctuation` 设置为`""`允许所有字符等同于禁用规则

### MD027-块引用符号后的多个空格

``` markdown
error:
>  1
>  2

success:
> 1
> 2
```

### MD028-块引用内的空白行

``` markdown
error:
> 1

> 3

success:
> 1
text
> 3
或者
> 1
>
> 3
```

### MD029-有序列表项的前缀
**params**: `style` ("one", "ordered", "one_or_ordered", "zero"; default "one_or_ordered")

``` markdown
one
1. Do
1. Do .

ordered
1. Do
2. Do

zero
0. Do
0. Do
```

### MD030-列表标记后的空格
**params**: `ul_single, ol_single, ul_multi, ol_multi` (number; default 1)

### MD031-命令行代码块用空行包围
**params**: `list_items` (boolean; default true)

### MD032-列表应由空行包围

### MD033-内联HTML
**params**: `allowed_elements` (array of string; default empty)

``` markdown
allowed_elements: [
    "pre",
    "span"
]
```

### MD034-裸链接必需使用 `<https://www.example.com/>`

### MD035-hr样式
**params**: `style` ("consistent", "---", "***", 或其他指定水平线的字符串; default "consistent")

### MD036-使用强调代替标题
**params**: `punctuation` (string; default ".,;:!?。，；：！？")

``` markdown
error:

**我的文件**

小学二年级奥数试题及答案小学奥数网...

_另一部分_

奉献精英，sed做eiusmod。

success: 请使用markdown标题而不是强调文本来表示部分

## 我的文件

小学二年级奥数试题及答案小学奥数网...

### 另一部分

奉献精英，sed做eiusmod。
```

### MD037-重点标记内符号跟文本之间不能有空格 `**效果:** **加醋** __加粗__ *倾斜* _斜体_ ***加粗斜体*** ___加粗斜体___ ~~删除线~~`

### MD038-单行代码块符号跟文字之间不能有空格

``` markdown
error: ` some text `
success: `some text`
```

### MD039-链接文本内符号跟文本之间不能有空格

``` markdown
error: [ link ](https://www.example.com)
success: [link](https://www.example.com)
```

### MD040-多行代码块需要指定代码语言

<pre>
``` bash
echo Hello word
```
</pre>

### MD041-文件中的第一行应为顶层标题
**params**: `level, front_matter_title` (number; default 1, string; default "^\s*title:")

### MD042-不能是空链接

``` markdown
error: [an empty link]()

success
[a valid link](https://example.com/)
[an empty fragment](#)
[a valid fragment](#fragment)
```

### MD043-必需的标题结构
**params**:  `headings, headers` (array of string; default null for disabled)

``` markdown
headings: [
    "# Head",
    "## Item",
    "### Detail"
]
```

### MD044-配置专有名称
**params** `names, code_blocks` (string array; default null, boolean; default true)

- `names`: 当names数组中的任何字符串不具有指定的大写字母时，将触发此规则。它可以用于对项目和产品的名称强制使用标准字母大小写
- `code_blocks`: 将code_blocks参数设置false为禁用此规则的代码块

``` markdown
names: [
    "JavaScript",
    "Html"
]
```

### MD045-图片应具有替代文字

### MD046-代码块样式
**params**: `style` ("consistent", "fenced", "indented"; default "consistent")

### MD047-文件应以单个换行符结尾
