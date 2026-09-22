# beamer-thusem

**English** | [简体中文](README.zh-CN.md)

Personal beamer theme in the Tsinghua SEM "Oriental Blue" identity.

- Standard colour `#0000A8` (PANTONE Blue 072) and the blue auxiliary
  palette (Blue 10/20/40/60/80/100) from the SEM Visual Identity
  Guidelines (2021 edition). Alerts use Orange 60 as the single accent;
  example blocks use Blue 60.
- Classic academic beamer layout (Madrid / thubeamer style): solid blue
  title bar with the emblem, rounded blocks with shadows, rounded title
  box, circle bullets, frame number in the footline.
- Vector SEM emblem converted from the official SVG (`thusem-emblem.pdf`,
  `thusem-emblem-white.pdf`); wide logo PNGs kept for optional use.
- Fonts: Microsoft YaHei for all Chinese text, Arial for Latin letters
  and digits; math in newtxmath (Times-like, matching thuthesis) with
  the rsfs script alphabet for `\mathcal`. YaHei is read
  from the Word bundle (`\thusemwordfontpath`, default
  `/Applications/Microsoft Word.app/Contents/Resources/DFonts/`);
  redefine that macro before `\usetheme` if Word lives elsewhere.
- Structure adapted from `thubeamer` (CTAN, LPPL 1.3c) and
  `tuna/THU-Beamer-Theme`.

## Files

```
beamerthemethusem.sty      the theme
thusem-emblem.pdf          SEM emblem, Oriental Blue
thusem-emblem-white.pdf    SEM emblem, white (used in the frame-title bar)
thusem-logo-wide.png       emblem + SEM + full name, horizontal (optional)
thusem-logo-wide-white.png white version of the above (optional)
thusem-example.tex         minimal example
```

## Usage

Compile with XeLaTeX (latexmk: `latexmk -pdfxe file.tex`).

Either copy the `.sty` and the two emblem PDFs next to your slides, or
point LaTeX at this folder from the top of the document:

```latex
\makeatletter
\providecommand*{\input@path}{}
\g@addto@macro\input@path{{/path/to/beamer-thusem/}}
\makeatother
\documentclass[aspectratio=169,10pt]{beamer}
\usetheme{thusem}          % options: en, noemblem
```

Helpers:

- `\thusemclosing{<main line>}{<sub line>}` produces the closing frame
  in the same layout as the title page (author, institute and date are
  repeated).
- Footline shows the frame number only.
- Colours `thusemBlue`, `thusemBlue100`, `thusemBlue80`, `thusemBlue60`,
  `thusemBlue40`, `thusemBlue20`, `thusemBlue10`, `thusemOrange`, `thusemGray` are
  available.

## License

The theme files (`beamerthemethusem.sty`, `thusem-example.tex`) are
released under the LaTeX Project Public License 1.3c; see `LICENSE`.
The SEM emblem and logo files are trademarks of the School of Economics
and Management, Tsinghua University, and are included only for use by
members of the school; they are not covered by the LPPL.
