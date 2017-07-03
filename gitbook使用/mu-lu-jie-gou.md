# 目录结构

GitBook使用简单的目录结构。摘要中列出的所有Markdown / Asciidoc文件将被转换为HTML。多语言书籍结构略有不同。

一个基本的GitBook通常看起来像这样：

``` javacript

├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md

```


```
ss
```


概述这些功能是什么：
文件	描述
book.json	存储配置数据（可选）
README.md	您的书的前言/介绍（必填）
SUMMARY.md	目录（见页）（可选）
GLOSSARY.md	词汇/注释术语列表（见词汇表）（可选）