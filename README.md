# lingoread-data

LingoRead（小五英语跟读背诵）的**公开示例数据仓库**。

这里只放可自由分发的示例内容：原创词表、公版童谣、公版寓言、常见谚语。
**不放教材原文**——人教 PEP 等教材内容受著作权保护，不适合公开发布。

---

## 家长怎么用

打开 LingoRead → 对应模块 → **导入** → **从网址** → 粘贴下面任一链接 → 获取。

### 单词

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/words/animals-and-nature.csv
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/words/daily-verbs.csv
```

### 朗读

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/reading/my-day.csv
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/reading/twinkle-twinkle-little-star.csv
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/reading/aesop-the-lion-and-the-mouse.csv
```

### 金句

```
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/motto/common-proverbs.csv
https://raw.githubusercontent.com/JargeZhu/lingoread-data/main/motto/aesop-lessons.csv
```

### 打不开怎么办

不同网络对 GitHub 域名的可达性不一样，换下面任一形式，内容完全一致：

| 形式 | 模板 | 实测 |
|---|---|---|
| GitHub raw | `https://raw.githubusercontent.com/{owner}/{repo}/main/{path}` | 0.6s ✅ |
| ghfast 代理 | `https://ghfast.top/https://raw.githubusercontent.com/{owner}/{repo}/main/{path}` | 0.6s ✅ |
| jsDelivr Fastly | `https://fastly.jsdelivr.net/gh/{owner}/{repo}@main/{path}` | 0.7s ✅ |
| jsDelivr Gcore | `https://gcore.jsdelivr.net/gh/{owner}/{repo}@main/{path}` | 3.5s+ 偶发超时 |

> `cdn.jsdelivr.net`（不带节点前缀）在 2026-10 实测**不可用**，不要用。

---

## 自己整理的数据怎么发布

见 [`schema/csv-fields.md`](schema/csv-fields.md) 里的字段规范。三套 CSV 的列顺序只要带表头就可以任意排，
表头别名见文档。

---

## 目录

```
words/     单词表，每行一个单词
reading/   朗读课文，同一「标题」的多行会自动合并成一篇
motto/     金句，每行一条
schema/    字段规范说明
```

文件**必须直接放在三个目录下**，不支持子目录。
