---
title: "QUIC相关翻译说明"
anchor: "QUIC_Related"
weight: 110
rank: "h1"
---

## 1. 帧类型翻译展示

`ACK`、`STREAM`、`NEW_CONNECTION_ID`等帧类型如果直接使用原文实为不妥，并不直观。然而，其又以大写形式表现，固所以需要进行特别处理。

本文决定暂时采用将其加粗展示的方式进行区分。

## 2. 帧字段翻译展示
如下是重置帧的定义：
```
RESET_STREAM Frame {
  Type (i) = 0x04,
  Stream ID (i),
  Application Protocol Error Code (i),
  Final Size (i),
}
```
其中Type、Stream ID等均是帧字段。
用“”将字段括起来。

## 2. 错误类型翻译展示

形如`CONNECTION_ID_LIMIT_ERROR`的错误类型也比较麻烦，因其可能细碎地提前引用。因此，需要将其特别考虑。
在其正式介绍前，如果首次出现在一个大章节中，则该大写字段以括号（）附上中文翻译。同章节后续再出现则不再附上翻译。

## 3. 传输参数翻译展示

传输参数（transport parameters）展示方式同第2点。