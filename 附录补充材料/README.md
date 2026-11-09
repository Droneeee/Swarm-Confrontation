# 学位论文在线补充材料

本目录是《海上异构无人集群对抗防御决策研究》的独立补充材料包。内容从论文附录中拆出，未新增原论文不存在的研究内容。

## 文件清单

- `appendix_supplement.pdf`：编译后的补充材料 PDF。
- `appendix_supplement.tex`：独立编译入口。
- `sections/appendices_content.tex`：技术说明和提示词模板。
- `sections/raw_data_tables.tex`：第三至第五章主要实验的原始数据附表。
- `figures/轨迹压缩.png`：平台轨迹压缩示意图。
- `figures/热点区域中心示意图.png`：热点方向补偿示意图。

## 本地编译

需要安装包含中文支持的 TeX 发行版（推荐 TeX Live），然后在本目录执行：

```powershell
xelatex -interaction=nonstopmode -halt-on-error appendix_supplement.tex
xelatex -interaction=nonstopmode -halt-on-error appendix_supplement.tex
```

第二次编译用于更新目录和交叉引用。文档依赖 `ctex`、`amsmath`、`graphicx`、`algorithm`、`algpseudocode`、`adjustbox`、`booktabs`、`rotating`、`caption`、`setspace`、`xurl` 和 `hyperref` 等常见宏包。
