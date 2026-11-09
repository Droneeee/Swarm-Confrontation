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

## 建议的仓库位置

建议将整个目录上传到仓库中的 `supplementary-materials/thesis-appendix/`，保留现有相对目录结构。可在仓库主 `README.md` 中添加以下入口：

```markdown
## Thesis supplementary materials

- [Compiled appendix (PDF)](supplementary-materials/thesis-appendix/appendix_supplement.pdf)
- [LaTeX source](supplementary-materials/thesis-appendix/appendix_supplement.tex)
```

## 上传与认证

只在 GitHub 网页上传文件时，登录有该仓库写权限的 GitHub 账号即可，不需要另行创建密钥。

如果使用命令行推送，推荐以下任一方式：

1. 使用 GitHub CLI 执行 `gh auth login`，按提示通过浏览器登录；
2. 使用 HTTPS 和细粒度个人访问令牌（fine-grained PAT），令牌仅授权此仓库，并只授予 `Contents: Read and write`；
3. 使用 SSH 密钥：将公钥添加到 GitHub，私钥只保存在本机，不要上传到仓库。

任何令牌、私钥、API Key、`.env` 文件或账号密码均不得放入本目录或提交历史。GitHub Actions 如仅需读取仓库并编译文档，通常使用工作流自动提供的 `GITHUB_TOKEN`，无需把个人令牌写入 YAML。

## 发布前检查

- 确认 PDF 可以打开，目录、公式、算法、图片和横向数据表显示正常；
- 确认 TeX 中没有未定义引用；
- 确认两张图片随源文件一同上传；
- 对整个仓库执行密钥扫描，清除硬编码的 API Key、令牌和私钥；
- 若单个文件超过 GitHub 网页上传限制，改用 Git 命令行；超过普通 Git 文件上限时使用 Git LFS 或 Release 附件；
- 建议新建分支提交并通过 Pull Request 合并，便于检查文件和回退。
