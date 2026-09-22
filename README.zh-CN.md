# beamer-thusem

[English](README.md) | **简体中文**

清华大学经济管理学院“东方蓝”视觉风格的个人 beamer 主题。

- 主色为经管院标准色 `#0000A8`（PANTONE Blue 072），辅色采用《清华大学经济管理学院视觉形象指导手册（2021 版）》中的蓝色系列（Blue 10/20/40/60/80/100）。强调色仅用 Orange 60 一种；example block 用 Blue 60。
- 版式为常规学术 beamer 风格（近似 Madrid / thubeamer）：蓝色实心标题栏并带院徽，圆角阴影 block，圆角封面标题框，圆点项目符，页脚仅显示页码。
- 院徽由官方 SVG 转为矢量 PDF（`thusem-emblem.pdf`、`thusem-emblem-white.pdf`），另附横向组合 logo 的 PNG 供选用。
- 字体：中文全部为微软雅黑，字母和数字为 Arial；公式使用 newtxmath（Times 风格，与 thuthesis 一致），花体 `\mathcal` 取自 rsfs。微软雅黑从 Word 自带字体目录读取（宏 `\thusemwordfontpath`，默认 `/Applications/Microsoft Word.app/Contents/Resources/DFonts/`）；若 Word 安装在其他位置，请在 `\usetheme` 之前重新定义该宏。
- 结构参考了 `thubeamer`（CTAN，LPPL 1.3c）与 `tuna/THU-Beamer-Theme`。

## 文件

```
beamerthemethusem.sty      主题文件
thusem-emblem.pdf          经管院院徽，东方蓝
thusem-emblem-white.pdf    经管院院徽，反白（用于标题栏）
thusem-logo-wide.png       院徽 + SEM + 全称横向组合（可选）
thusem-logo-wide-white.png 上一文件的反白版（可选）
thusem-example.tex         最小示例
```

## 用法

使用 XeLaTeX 编译（latexmk：`latexmk -pdfxe file.tex`）。

可以把 `.sty` 和两个院徽 PDF 复制到幻灯片所在目录，也可以在文档开头指定本目录的路径：

```latex
\makeatletter
\providecommand*{\input@path}{}
\g@addto@macro\input@path{{/path/to/beamer-thusem/}}
\makeatother
\documentclass[aspectratio=169,10pt]{beamer}
\usetheme{thusem}          % 可选参数：en, noemblem
```

辅助命令：

- `\thusemclosing{<主标题>}{<副标题>}` 生成与封面同一版式的封底（作者、单位、日期会重复显示）。
- 页脚只显示页码。
- 可用颜色：`thusemBlue`、`thusemBlue100`、`thusemBlue80`、`thusemBlue60`、`thusemBlue40`、`thusemBlue20`、`thusemBlue10`、`thusemOrange`、`thusemGray`。

## 许可

主题文件（`beamerthemethusem.sty`、`thusem-example.tex`）按 LaTeX Project Public License 1.3c 发布，见 `LICENSE`。院徽和 logo 文件为清华大学经济管理学院的标识，仅供本院师生使用，不在 LPPL 覆盖范围内。
