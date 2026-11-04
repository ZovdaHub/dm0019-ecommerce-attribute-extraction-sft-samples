# DM0019 · E-commerce Attribute Extraction SFT Samples / 电商商品属性抽取 SFT 样例

**Dataset card / 数据集卡片** · Zovda sample dataset. This repository is the GitHub mirror of the card; the data files are hosted on Hugging Face — **[download the dataset / 下载数据集](https://huggingface.co/datasets/Zovda/dm0019-ecommerce-attribute-extraction-sft-samples)**.

本仓库是数据集卡片的 GitHub 镜像，数据文件托管在 Hugging Face，**[点击下载 / download](https://huggingface.co/datasets/Zovda/dm0019-ecommerce-attribute-extraction-sft-samples)**。

| Item / 项目 | Value / 值 |
|---|---|
| Dataset ID / 数据集编号 | DM0019 |
| Files / 数据文件 | 0 |
| Size / 数据体积 | 0 B |
| Language / 语言 | zh |
| Tasks / 任务类别 | text-generation, text-classification |
| Hugging Face / 数据地址 | [dm0019-ecommerce-attribute-extraction-sft-samples](https://huggingface.co/datasets/Zovda/dm0019-ecommerce-attribute-extraction-sft-samples) |
| Provided by / 提供方 | Zovda |
| Contact / 联系邮箱 | lucas@zovda.com |

## Overview / 简介

Structured SFT corpus for e-commerce attribute extraction: every record carries instruction, input, output and field-level evidence chains, in full-text and title-only forms — 2,808 records, v2.1.1 signed off after passing 39/39 QC checks.

面向电商商品属性抽取的结构化 SFT 语料：每条记录含指令、输入、输出与字段级证据链，覆盖「全文（标题+详情）」与「仅标题」两种形态，2,808 条记录，v2.1.1 签版质检 39/39 全过。

## What's inside / 数据内容

- `main`: full-text extraction from title + detail, 1,485 records (1,170 with brand).
- `main` 形态：基于标题 + 详情文本的全文抽取，1,485 条（含品牌 1,170 条）。
- `title_only`: only attributes with title evidence, no guessing — 1,323 records (789 with brand), paired with `main`.
- `title_only` 形态：仅输出标题中有证据的属性、不臆测，1,323 条（含品牌 789 条），与 `main` 同源成对。
- `evidence_hit` logs, per field, the raw span → normalised value / trigger word → hit result, plus the drop reason for discarded attributes (`no_evidence` / `junk_value` / `noinfo_value`).
- `evidence_hit` 逐字段记录 raw 原文 → 规范值 / 驱动词 → 命中结果，并记录被丢弃属性的原因（`no_evidence` / `junk_value` / `noinfo_value`）。
- Archive files are delivered on request — contact lucas@zovda.com. This page documents the full schema with real examples.
- 样例归档文件按需交付，请联系 lucas@zovda.com；本页给出完整字段结构与真实样例。

## Specifications / 规格

- Record schema v2: `instruction` / `input` / `output` / `evidence_hit` / `meta`
- 记录 schema v2：`instruction` / `input` / `output` / `evidence_hit` / `meta`
- Output is normalised attribute JSON: keys are canonical attribute names, values are canonical values
- 输出为规范属性 JSON：键为标准属性名，值为规范值
- Version: v2.1.1 (signed off 2026-09-18, frozen baseline)
- 版本：v2.1.1（2026-09-18 签版，冻结基线）

## Suitable tasks / 适用任务

- Attribute extraction and listing-information extraction
- 属性抽取与商品刊登上架信息抽取
- Evidence-constrained output: emit only when evidence exists, suppressing hallucination
- 证据约束输出：仅在有证据时输出，抑制幻觉
- Title-only vs full-text information-boundary training and evaluation
- 「仅标题 vs 全文」信息边界对照训练与评测
- Product data governance and consistency review
- 商品数据治理与一致性审核

## Files / 文件清单

Paths below are relative to the Hugging Face repository root. 下表路径相对于 Hugging Face 仓库根目录。

_本数据集为说明页：样例文件按需交付，请联系 lucas@zovda.com 获取。_

_This card is documentation-only: sample files are delivered on request — contact lucas@zovda.com._

## Download / 下载

The files are not stored in this repository. 数据文件不在本仓库内，请从 Hugging Face 获取。

- Dataset page / 数据集页面: https://huggingface.co/datasets/Zovda/dm0019-ecommerce-attribute-extraction-sft-samples
- Direct file URL / 单文件直链: `https://huggingface.co/datasets/Zovda/dm0019-ecommerce-attribute-extraction-sft-samples/resolve/main/<path from MANIFEST.csv>`

```python
from huggingface_hub import snapshot_download

snapshot_download(
    repo_id="Zovda/dm0019-ecommerce-attribute-extraction-sft-samples",
    repo_type="dataset",
    local_dir="./dm0019-ecommerce-attribute-extraction-sft-samples",
)
```

```python
from huggingface_hub import hf_hub_download

hf_hub_download(
    repo_id="Zovda/dm0019-ecommerce-attribute-extraction-sft-samples",
    repo_type="dataset",
    filename="<path from MANIFEST.csv>",
    local_dir="./dm0019-ecommerce-attribute-extraction-sft-samples",
)
```

## Rights and disclaimer / 授权与声明

Text derives from public product-page snapshots and remains the property of their rightsholders. Samples demonstrate schema and annotation conventions; contact us for commercial licensing.

文本来源于公开商品详情页快照，著作权归相应权利人。样例用于展示字段结构与标注口径；商用授权请联系我们。

This dataset is shared to demonstrate data organisation, technical specifications and delivery structure. For formal licensing, large-scale access or custom production, contact lucas@zovda.com.

本数据集仅用于展示数据组织方式、技术规格与交付结构。正式授权、规模化取数与定制生产请联系 lucas@zovda.com。

## About Zovda / 关于 Zovda

Zovda builds, cleans, annotates and packages training data across video, audio, images, e-commerce image-text pairs, exam question banks, embodied AI and coding-agent corpora.

Zovda 提供多模态与文本训练语料的数据采集、清洗、标注与结构化交付服务，覆盖视频、音频、图像、电商图文、K12 与职业题库、具身智能、代码智能体等方向。

**Contact / 联系方式:** lucas@zovda.com
