# City Strength Comparison Model v2

[简体中文](README.md) · [English](README.en.md)

A reproducible MATLAB model for comparing any two Chinese cities across:

- 270 public indicators
- 12 categories
- weighted hard-power and soft-power dimensions
- category-level wins, losses, and relative strength

The goal is not to produce an authoritative ranking. The goal is to make the assumptions visible: indicators, weights, data years, sources, redundancy discounts, and scoring rules are all stored in editable CSV files.

## What you get

| Input | Output |
|---|---|
| A weight table | Hard, soft, and overall advantage |
| A two-city data table | Weighted results for 12 categories |
| Two city names | Win/loss counts and a relative strength index |
| Data years and sources | Four reproducible files: CSV, CSV, TXT, and PNG |

## Quick start

1. Download [city_pair_model_v2.m](city_pair_model_v2.m), [通用权重v2.csv](通用权重v2.csv), and [数据模板v2.csv](数据模板v2.csv).
2. Put them in the same folder.
3. Run the model in MATLAB:

```matlab
city_pair_model_v2('通用权重v2.csv', '数据表.csv', '杭州', '成都', '杭州成都')
```

## Example result

![Hangzhou vs Chengdu category comparison](docs/images/example-category.png)

For Hangzhou vs Chengdu, the relative index is `89.92`: when Chengdu is indexed at 100, Hangzhou is approximately 89.92 on the current total-scale specification. The model also shows categories where Hangzhou leads, including technology innovation, finance, and industry.

## Why this is different

- It does not compare GDP alone.
- Correlated indicators receive redundancy discounts.
- Gaps use log-scored comparisons instead of binary win/loss scoring.
- Missing data stays missing instead of being silently converted to zero.
- Every result can be traced back to a data year and source.
- Weights and scoring rules are editable rather than hidden in code.

## Important limitations

This is a directional comparison tool, not an official ranking. Total-scale indicators tend to favor larger cities. Some categories have small sample sizes, and statistical scopes can differ between cities. The current `30% soft / 70% hard` weighting is a modeling choice, not an objective truth. Read the Chinese reports in [`docs/`](docs) for the full audit.

## Data sources

- Municipal statistical bulletins
- Municipal statistical yearbooks
- ShanghaiRanking university rankings
- Fudan hospital rankings
- National ministry and agency lists

## Contributing

- Request a city pair through the Chinese issue template.
- Submit data corrections with a verifiable source.
- Open a pull request for new indicators, weights, or an online version.
- If this project saves you time, a [GitHub Star](https://github.com/hwkiller-0314/city-comparison-model/stargazers) helps more people find it.

## Citation

See [CITATION.cff](CITATION.cff).

```bibtex
@software{chengshi_duibi_v2,
  title   = {城市综合实力比较模型 v2},
  author  = {hwkiller-0314},
  year    = {2026},
  url     = {https://github.com/hwkiller-0314/city-comparison-model}
}
```

## License

Code: [MIT](LICENSE). Papers and documentation: CC BY 4.0.
