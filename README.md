# Southeast Asian–Chinese Document-Level Parallel Corpus

Document-level parallel text for three Southeast Asian languages translated into Chinese. This repository contains the full collection only. It does not ship train, validation, or test splits.

## Files

| File | Source | Target | Pairs |
| --- | --- | --- | --- |
| `my-zh.json` | Burmese (`my`) | Chinese (`zh`) | 10,000 |
| `vi-zh.json` | Vietnamese (`vi`) | Chinese (`zh`) | 10,000 |
| `lo-zh.json` | Lao (`lo`) | Chinese (`zh`) | 10,000 |

## Format

Each file is a JSON list. One object is one document pair. Both sides are stored as a single string.

```json
[
  {"my": "<Burmese document>", "zh": "<Chinese document>"}
]
```

Vietnamese objects use the key `vi`. Lao objects use the key `lo`.

## Collection

The pairs were collected from Burmese–Chinese, Vietnamese–Chinese, and Lao–Chinese bilingual websites. The documents cover news and general topics, including politics, economy, culture, sports, and technology. No pair has an empty side.

## Length

Counts below are characters, not tokens.

| Direction | Source mean / median / min / max | Chinese mean / median / min / max |
| --- | --- | --- |
| Burmese–Chinese | 404 / 367 / 155 / 4,561 | 123 / 106 / 7 / 2,196 |
| Vietnamese–Chinese | 443 / 385 / 84 / 1,866 | 154 / 130 / 61 / 625 |
| Lao–Chinese | 422 / 358 / 144 / 1,854 | 145 / 123 / 33 / 634 |

## Load

```python
import json

pairs = json.load(open("my-zh.json", encoding="utf-8"))
print(len(pairs))
print(pairs[0]["my"])
print(pairs[0]["zh"])
```

## Use

The corpus is released for research on document-level machine translation. The text was gathered from public bilingual websites. Please also respect the terms of those sources.

## 说明

这是缅甸语、越南语、老挝语到汉语的篇章级平行语料，每个方向 10,000 条，不做训练、验证、测试划分。

- `my-zh.json`：字段 `my`、`zh`
- `vi-zh.json`：字段 `vi`、`zh`
- `lo-zh.json`：字段 `lo`、`zh`

每条是一个文档对，原文和中文各保存为一个字符串。语料来自对应的双语网站，题材包括政治、经济、文化、体育和科技等新闻与一般领域文本。
