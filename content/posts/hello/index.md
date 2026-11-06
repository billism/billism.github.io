+++
title = 'Hello'
date = 2026-11-06T15:00:00+08:00
draft = false
toc = true
math = true
description = '图文、表格、引用、代码、公式与古诗：一篇验证样式和排版的测试文章'
+++

这是一篇**测试文章**，用于检验站点的显示效果。


## 中英混排

中英混排: *Typography is the craft of endowing human language with a durable visual form.*（排版是赋予人类语言以持久视觉形式的技艺。）

## 图片

图片与 `index.md` 同目录，会自动懒加载：

```markdown
![Spanky](spanky.jpg)
```

需要图注以及居中时，可以用 `figure` shortcode：

```text
{{</* figure src="spanky.jpg" alt="Spanky (小顽童)" */>}}
```

{{< figure src="spanky.jpg" alt="Spanky" caption="Spanky (小顽童)">}}

## 表格

学术三线样式：

| 元素 | 写法 | 备注 |
|---|---|---|
| 图片 | `![alt](src)` | page bundle，自动懒加载 |
| 图注 | `figure` shortcode | 居中 + 小字体图注 |
| 古诗 | `poem` shortcode | 每行居中 |
| 公式 | 行内 `\(...\)`、显示 `$$…$$` | frontmatter 配置 `math = true` |

## 引用

> 「我没有特别的天赋，我只是极度好奇。」
>
> —— 阿尔伯特·爱因斯坦

英文引用的观感：

> "For instance, on the planet Earth, man had always assumed that he was more intelligent than dolphins because he had achieved so much — the wheel, New York, wars and so on — whilst all the dolphins had ever done was muck about in the water having a good time."
>
> — Douglas Adams

## 代码

代码块走 github / github-dark 双主题，跟随亮暗模式切换：

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, Achso!")
}
```

## 数学

行内：质能方程 \( E = mc^2 \)，欧拉公式 \( e^{i\pi} + 1 = 0 \)。正文里的美元符号不会被误判：这本书 $12.5。

显示公式：

\[
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
\]


## 古诗

`poem` shortcode，每行自动居中，可带题目与作者：

{{< poem title="静夜思" author="唐 · 李白" >}}
床前明月光，
疑是地上霜。
举头望明月，
低头思故乡。
{{< /poem >}}

英文诗：

{{< poem title="Ozymandias" author="Percy Bysshe Shelley" >}}
I met a traveller from an antique land,
Who said—"Two vast and trunkless legs of stone
Stand in the desert. . . . Near them, on the sand,
Half sunk a shattered visage lies, whose frown,
And wrinkled lip, and sneer of cold command,
Tell that its sculptor well those passions read
Which yet survive, stamped on these lifeless things,
The hand that mocked them, and the heart that fed;
And on the pedestal, these words appear:
My name is Ozymandias, King of Kings;
Look on my Works, ye Mighty, and despair!
Nothing beside remains. Round the decay
Of that colossal Wreck, boundless and bare
The lone and level sands stretch far away.
{{< /poem >}}

## 脚注

这一篇是带脚注的句子[^1]，上标不会撑大所在行的行距。

[^1]: 样例文章随时可整篇删除；写正式文章时用 `hugo new content posts/<slug>/index.md` 起步。
