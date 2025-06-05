# BUAA 未来空天项目开题报告模板

<div align="center">
  <img src="https://img.shields.io/badge/LaTeX-Project-blue" alt="LaTeX Project">
  <img src="https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey" alt="CC BY 4.0">
  <img src="https://img.shields.io/badge/BUAA-未来空天-red" alt="BUAA 未来空天">
</div>

<div align="center">
  <img src="https://user-images.githubusercontent.com/assets/latex-template-banner.png" alt="LaTeX模板展示" width="650">
</div>

## 项目简介

本项目为北京航空航天大学（BUAA）23系未来空天各种报告的LaTeX模板，改编自[开放原子能社团的北航毕设模板](https://github.com/BHOSC/BUAAthesis)。该模板提供了规范的开题报告格式，便于未来空天项目的学生快速生成符合要求的开题报告文档。

目前已包含模板：
未来空天进阶项目开题报告
机械设计基础（2）结题报告



## 目录结构

```
.
├── 开题报告 模板/
│   ├── style/           # 样式文件目录
│   ├── figure/          # 图片存放目录
│   ├── data/            # 内容数据目录
│   │   ├── bachelor/   
│   │   ├── abstract.tex # 摘要文件
│   │   ├── chapter1.tex # 第一章内容
│   │   ├── chapter2.tex # 第二章内容
│   │   ├── chapter3.tex # 第三章内容
│   │   ├── com_info.tex # 公共信息配置文件
│   │   └── reference.tex # 参考文献设置
│   ├── sample-bachelor.tex # 主LaTeX文件
│   └── bibs.bib         # 参考文献数据库
├── example.pdf          # 示例PDF文件
├── 开题报告 模板.zip     # 模板压缩包
├── LICENSE.md           # 许可证文件
└── README.md            # 项目说明文件
```

## 快速开始

### 1. 获取模板

直接下载本仓库中的`开题报告 模板.zip`文件并解压，或者克隆整个仓库：

```bash
git clone https://github.com/yourusername/wlkt-research-proposal.git
```

### 2. 环境依赖与安装

本模板需要安装LaTeX环境才能编译。推荐使用以下LaTeX发行版之一：

#### Windows系统
- [TeX Live](https://www.tug.org/texlive/) (推荐)
- [MikTeX](https://miktex.org/)

#### macOS系统
- [MacTeX](https://www.tug.org/mactex/)

#### Linux系统
- TeX Live：通过包管理器安装，例如 Ubuntu 系统：
  ```bash
  sudo apt-get install texlive-full
  ```

#### 在线编辑
- [Overleaf](https://www.overleaf.com/)：可将模板上传至Overleaf在线编辑和编译

#### 额外依赖包
确保你的LaTeX环境安装了以下宏包：
- ctex: 中文支持
- graphicx: 图像处理
- hyperref: 创建超链接
- geometry: 页面布局
- booktabs: 表格美化
- natbib/gbt7714: 参考文献格式

### 3. 个人信息配置

编辑以下文件以自定义您的个人和项目信息：

- `data/com_info.tex`：设置学院、专业、论文标题、作者、导师等公共信息
- `data/bachelor/bachelor_info.tex`：设置学生特定信息

示例配置（`com_info.tex`）：

```latex
% 学院中英文名
\school{沈元}{School of XXX}

% 专业中英文名
\major{未来空天领军计划}{XXXX Engineering}

% 论文中英文标题
\thesistitle{开题报告标题}{English Title}
```

### 4. 编写报告内容

主要内容位于`data/`目录下的各章节文件中：

- `chapter1.tex`
- `chapter2.tex`
- `chapter3.tex`
- `abstract.tex`

### 5. 编译文档

使用LaTeX编译工具（如TeXLive、MikTeX等）编译`sample-bachelor.tex`文件：

```bash
pdflatex sample-bachelor.tex
bibtex sample-bachelor
pdflatex sample-bachelor.tex
pdflatex sample-bachelor.tex
```

或使用支持LaTeX的编辑器（如TeXstudio、Overleaf等）打开并编译。

## 新增格式说明

本模板定义了一种新格式`\chapter{}`，对应原模板中的大板块标题。如不需要目录，请自行注释掉主文件中的`\tableofcontents`代码。

## 参考文献

参考文献使用GBT7714格式，可通过设置`\citestyle{numerical}`或`\citestyle{authoryear}`在两种引用方式之间切换：
- `numerical`：按照出现顺序编号引用
- `authoryear`：按照作者姓名和年份引用

## 详细使用指南

### 模板基本用法

1. **文档结构**：模板主体在`sample-bachelor.tex`文件中，通过引入各个章节文件组合成完整论文
   
2. **文档类设置**：
   ```latex
   \documentclass[bachelor,openany,oneside,color,twoteacher]{style/buaathesis}
   ```
   其中可选参数包括：
   - `bachelor`：本科生论文格式
   - `openany`：章节可以从任意页开始
   - `oneside/twoside`：单面/双面打印格式
   - `color`：启用彩色链接
   - `twoteacher`：双导师模式

3. **添加章节**：
   ```latex
   \chapter{章节标题}  % 大标题
   \section{节标题}    % 一级小标题
   \subsection{小节标题} % 二级小标题
   ```

4. **插入图片**：
   ```latex
   \begin{figure}[htbp]
     \centering
     \includegraphics[width=0.8\textwidth]{figure/图片名称}
     \caption{图片标题}
     \label{fig:标签名}
   \end{figure}
   ```
   
5. **插入表格**：
   ```latex
   \begin{table}[htbp]
     \centering
     \caption{表格标题}
     \begin{tabular}{ccc}
       \toprule
       表头1 & 表头2 & 表头3 \\
       \midrule
       内容1 & 内容2 & 内容3 \\
       \bottomrule
     \end{tabular}
     \label{tab:标签名}
   \end{table}
   ```

6. **引用参考文献**：
   ```latex
   正文中引用\cite{参考文献标识}
   ```
   参考文献在`bibs.bib`文件中定义

### 模板进阶用法

1. **自定义页眉页脚**：在`style/buaathesis.cls`文件中查找页眉页脚相关设置

2. **修改字体**：在`style/buaathesis.cls`文件中查找字体相关设置

3. **增加附录**：
   ```latex
   \appendix
   \chapter{附录标题}
   附录内容
   ```

## 常见问题 (FAQ)

### Q1: 如何修改字体大小？
**A**: 可以使用`\zihao{数字}`命令修改字体大小，例如`\zihao{4}`表示四号字体。

### Q2: 如何解决编译时的"找不到文件"错误？
**A**: 请确保所有引用的文件（图片、参考文献等）都放在正确的目录中，并且文件名没有特殊字符或空格。

### Q3: 参考文献编译后没有显示怎么办？
**A**: 请确保按照以下顺序编译：
```
pdflatex sample-bachelor.tex
bibtex sample-bachelor
pdflatex sample-bachelor.tex
pdflatex sample-bachelor.tex
```

### Q4: 如何在表格中使用竖线？
**A**: 在tabular环境的列格式中使用`|`符号，例如：
```latex
\begin{tabular}{|c|c|c|}
```

### Q5: 如何增加行间距？
**A**: 可以使用`\linespread{倍数}`命令，例如`\linespread{1.5}`表示1.5倍行距。

## 示例预览

<div align="center">
  <p>查看 <a href="example.pdf">example.pdf</a> 获取完整示例</p>
  
  <table>
    <tr>
      <td><img src="https://user-images.githubusercontent.com/assets/latex-cover.png" alt="封面示例" width="400"></td>
      <td><img src="https://user-images.githubusercontent.com/assets/latex-content.png" alt="内容示例" width="400"></td>
    </tr>
    <tr>
      <td align="center">封面示例</td>
      <td align="center">内容页示例</td>
    </tr>
  </table>
</div>

## 贡献指南

我们非常欢迎您对本项目做出贡献！以下是参与方式：

1. **提交Bug或功能建议**：通过GitHub Issue提交您发现的问题或建议
2. **提交改进**：Fork本仓库，修改后提交Pull Request
3. **完善文档**：帮助我们改进文档和使用说明

请确保您的贡献符合以下要求：
- 遵循已有的代码和文档风格
- 添加必要的注释和文档
- 对重要变更进行测试

## 许可证

本项目采用[Creative Commons Attribution 4.0 International License](LICENSE.md)许可。

## 联系方式

如有任何问题，请联系：
- 微信：13757889425
- 邮箱：suyingke@buaa.edu.cn

## 致谢

感谢[开放原子能社团](https://github.com/BHOSC/BUAAthesis)提供的原始北航毕设模板。
