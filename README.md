# lingoread-data

铃谷晨读（小学英语跟读背诵）的**公开数据仓库**。

打开铃谷晨读 → 设置页 → **导入单词 / 导入文章 / 导入金句** → **从网址** → 粘贴下面任一链接 → 获取。

---

## 有什么数据

| 模块 | 文件 | 内容 | 条目 |
|---|---|---|---|
| 单词 | [`words/grade1-6-words.csv`](words/grade1-6-words.csv) | 小学 1-6 年级词汇，含音标、释义、例句（库名列区分一年级上册~六年级下册，共 12 个库） | 606 词 |
| 单词 | [`words/grade1-6-extension-words.csv`](words/grade1-6-extension-words.csv) | 小学英语扩展词汇，导入后是一个库（涵盖学习用品、动物、食物、动词等 37 类主题） | 568 词 |
| 单词 | [`words/grade7-9-words.csv`](words/grade7-9-words.csv) | 初中 7-9 年级词汇，含音标、释义、例句（库名列区分七年级上册~九年级下册，共 6 个库） | 823 词 |
| 单词 | [`words/grade7-9-extension-words.csv`](words/grade7-9-extension-words.csv) | 初中扩展词汇，导入后是一个库 | 569 词 |
| 朗读 | [`reading/nursery-rhymes.csv`](reading/nursery-rhymes.csv) | 10 首经典英文儿歌，逐句中英对照 | 10 篇 |
| 金句 | [`motto/shakespeare-quotes.csv`](motto/shakespeare-quotes.csv) | 莎士比亚名句与经典台词，含分类 | 170 条 |

每个文件都是**纯 UTF-8 CSV**，列名可读，用 Excel 或记事本就能改。
字段规范见 [`schema/csv-fields.md`](schema/csv-fields.md)。

---

## 导入链接

### 单词：小学 1-6 年级（606 词，12 个库）

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/words/grade1-6-words.csv
```

### 单词：小学英语扩展词汇（568 词，1 个库）

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/words/grade1-6-extension-words.csv
```

### 单词：初中 7-9 年级（823 词，6 个库）

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/words/grade7-9-words.csv
```

### 单词：初中扩展词汇（569 词，1 个库）

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/words/grade7-9-extension-words.csv
```

### 朗读（10 首儿歌）

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/reading/nursery-rhymes.csv
```

### 金句（170 条）

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/motto/shakespeare-quotes.csv
```

---

## 打不开怎么办

不同网络对 GitHub 域名的可达性差别很大，**换下面任一形式即可，内容完全一致**：

| 形式 | 模板 |
|---|---|
| GitHub raw | `https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/<路径>` |
| ghfast 代理 | `https://ghfast.top/https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/<路径>` |
| jsDelivr（Fastly） | `https://fastly.jsdelivr.net/gh/JargeZhu/lingoread-data@main/<路径>` |
| jsDelivr（Gcore） | `https://gcore.jsdelivr.net/gh/JargeZhu/lingoread-data@main/<路径>` |

> `cdn.jsdelivr.net`（不带节点前缀）在 2026-10 实测不可用，别用。
>
> **邮箱附件链接、网盘分享链接、腾讯文档/石墨的「导出」链接一律不行**——那些地址要登录态或返回网页，
> App 拿到的是 HTML 而不是 CSV，会提示「内容不是表格」。

---

## 版本与校验

- 分支 `main` 始终是最新内容，上面的链接可直接用。
- `catalog.json` 是机器可读清单：每个文件的字节数、条目数、`sha256`。
  发布新版本时重打一个 tag（形如 `v2026.10.19`），`catalog.json` 的 `ref` 指向它，
  这样「清单」和「文件」永远同版本。
- 想确认下载到的是否完整，可对比 `sha256`：

  ```bash
  sha256sum grade1-6-words.csv
  # PowerShell: Get-FileHash grade1-6-words.csv -Algorithm SHA256
  ```

---

## 自己整理的数据怎么用

把 CSV 存成 UTF-8，按 [`schema/csv-fields.md`](schema/csv-fields.md) 的列名写好，
在 App 的导入页选「从文件」直接选这份 CSV 就行，**不需要用到这个仓库**。

- 列顺序随便排，只要有表头就能按列名认出来；
- 朗读表里同一个标题只需写一次，后面留空表示「还是这篇」；
- 文件上限 2 MB。

---

## 目录

```
words/     单词表，每行一个单词
reading/   朗读课文，同一「标题」的多行自动合并成一篇
motto/     金句，每行一条
schema/    字段规范说明
catalog.json  机器可读清单（字节数 / 条目数 / sha256）
```

文件**必须直接放在三个目录下**，不支持子目录。

---

## 内容来源与授权

本仓库数据由维护者整理，用于孩子在家练习。词表、歌词、名言原文均来自公开可查的常见材料。

如果某份内容侵犯了你的权益，请开 issue，收到后会立即删除。

**注意**：仓库内容不保证与任何教材版本逐字一致，请以孩子的课本为准。
