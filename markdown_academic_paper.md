### 步骤
#### pandoc 生成word模板

```css
pandoc --print-default-data-file reference.docx > custom-reference.docx
```
#### 修改custom-reference.docx的样式

### 相关语法
- 按照模板输出文件
```css
pandoc --reference-doc=<ref.docx> <test_paper.md> -o <test_paper.docx>
```
- 复杂语句
```css
pandoc --citeproc --bibliography=<ref.bib> --csl=<china-national-standard-gb-t-7714-2015-numeric.csl> --filter pandoc-crossref -M reference-section-title=<"参考文献"> -M link-citations=true <系统应用AI思路.md> -o <test_paper.docx>
```
- pandoc转换其他格式文档
```css
pandoc -F pandoc-crossref --citeproc <file.md> -o <file.html>
```
- 较全的语句
```css
  pandoc -F pandoc-crossref -M figureTitle=<"图"> -M figPrefix=<"图"> --reference-doc=<custom-reference.docx> --citeproc --bibliography=<ref.bib> --csl=<china-national-standard-gb-t-7714-2015-numeric.csl> -M reference-section-title=<"参考文献"> -M link-citations=true <系统应用AI思路.md> -o <test_paper.docx>
```
- 带配置文件的语句
```css
pandoc -F pandoc-crossref --citeproc --bibliography=<ref.bib> --reference-doc=<custom-reference.docx> --metadata-file <config.yaml> <系统应用AI思路.md> -o <test_paper.docx>
```
### 参考
- [学术论文写作新武器：Markdown-中篇](https://zhuanlan.zhihu.com/p/367675732)
- [用markdown写论文终章｜实例篇](https://zhuanlan.zhihu.com/p/412817834)