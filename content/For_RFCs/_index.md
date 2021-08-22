---
title: "RFC文档翻译规范"
anchor: "For_RFCs"
weight: 100
---

## 1. 方括号引用参考文献

形如：

```markdown
The integration of TLS and QUIC is described in more detail in [[QUIC-TLS](#QUIC-TLS)].
```

[QUIC-TLS]是句子里实际提到的参考文献，这个结构本身参与语法构建，按照中文的习惯一般使用书名号《》将这种引用括起来。因此其应该翻译为：

```
《[QUIC TLS](#QUIC-TLS)》
```

但是下述这种：

```markdown
QUIC integrates the TLS handshake [[TLS13](#TLS13)].
```

[TLS13]并不是语句的一部分，更类似于书本中的上标或下标引用。本站将其统一用html的上标引用之：

```
TLS握手<sup>[TLS 1.3](#TLS13)</sup>
```

## 2. 图或表格

为了支持文档中的图及表格，这里fork了kraiklyn主题并添加了一个shortcode方法专门用来绘图及表格，例如：

```markdown
{{% block_ref
    indx="Table_1_Stream_ID_Types"
    title="表格1：流类型" %}}
\`\`\`
|位  |流类型|
|:---|:-----|
|0x00|客户端创建的双向流|
|0x01|服务端创建的双向流|
|0x02|客户端创建的单向流|
|0x03|服务端创建的单向流|
\`\`\`
{{% /block_ref %}}
```

这里，`block_ref`是专门定义的shortcode，`indx`用来指定锚点（请注意锚点不能使用的特殊字符），`title`表示图表名称。
`block_ref`会将`title`转成一个带跳转的href结构。引用该图表的方式：

```markdown
[表1](#Table_1_Stream_ID_Types)
```

## 3. 何时添加英语原文

只在如下情况添加：
- 在正式介绍一个名词的时候，在该章节其首次出现的地方用中文括号（）添加英语原文；
- 使用英语括号()括起来的一个名词或短语在翻译时使用中文括号（）括起来翻译内容，并在逗号后添加英语原文，逗号用中文；

