# Labelgrade Open Nutrition Dataset

**344 branded packaged foods + 74 whole foods, each graded A–F on a transparent, reproducible 6-dimension nutrition score — built entirely from public [USDA FoodData Central](https://fdc.nal.usda.gov/) data.** Licensed **CC BY 4.0** (free to use with attribution).

Maintained by **[Labelgrade](https://labelgrade.com)** — honest A–F grades for every branded food.
📊 Browse it online: **https://labelgrade.com/data** · 📐 Full methodology: **https://labelgrade.com/methodology**

---

## What's in it

| File | Rows | Description |
|---|---|---|
| `labelgrade-products.csv` / `.json` | **344** | Branded packaged products: per-serving macros + the full Labelgrade (overall score & letter + all six dimension sub-scores). |
| `labelgrade-foods.csv` / `.json` | **74** | Whole-food USDA references (e.g. chicken breast, plain Greek yogurt): macros per 100 g. |
| `labelgrade-dataset.json` | 344 + 74 | Combined products + foods + `meta` (version, generation date, weights). |

Every row carries its source `usda_fdc_id` (verify against USDA anytime) and a `report_url` linking to the full graded breakdown on labelgrade.com.

## The Labelgrade score (v3.1)

A weighted blend of six independently-scored (0–100) dimensions:

| Dimension | Weight |
|---|---|
| Protein density | 23% |
| Ingredient quality | 21% |
| Saturated fat load | 18% |
| Sodium load | 15% |
| Sugar load | 15% |
| Fiber | 8% |

Letter scale: **A+** ≥95 · **A** ≥90 · **A−** ≥85 · **B+** ≥80 · **B** ≥75 · **B−** ≥70 · **C+** ≥65 · **C** ≥60 · **C−** ≥55 · **D** ≥40 · **F** <40. Added sugar is penalized on a per-100g basis so small serving sizes can't hide it. The complete, fixed formula is published at **https://labelgrade.com/methodology**.

## Schema

**`labelgrade-products.csv`** — `slug, brand, product_name, category, upc, usda_fdc_id, serving_size, servings_per_package, calories, protein_g, total_fat_g, saturated_fat_g, total_carbs_g, fiber_g, sugars_g, added_sugars_g, sodium_mg, score, grade, protein_density_score, ingredient_quality_score, sugar_load_score, sodium_load_score, fiber_score, saturated_fat_score, last_verified, report_url`

**`labelgrade-foods.csv`** — `slug, food_name, common_portion, portion_grams, protein_g_per_100g, calories_per_100g, total_fat_g_per_100g, saturated_fat_g_per_100g, total_carbs_g_per_100g, fiber_g_per_100g, sugars_g_per_100g, sodium_mg_per_100g, usda_fdc_id, usda_data_type, last_verified, report_url`

## Example row

```
banza-chickpeas-pasta-penne-8-oz-227-g, Banza, "Chickpeas Pasta, Penne", … score 92, grade A …
→ https://labelgrade.com/banza-chickpeas-pasta-penne-8-oz-227-g
```

## Source, license & citation

- **Source data:** USDA FoodData Central (U.S. public domain). The Labelgrade scoring layer is original work by Labelgrade.
- **License:** [Creative Commons Attribution 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) — use it freely, commercially or not, with attribution.
- **Attribution:** *Labelgrade — https://labelgrade.com*
- **How to cite:**
  > Labelgrade. *Labelgrade Open Nutrition Dataset.* 2026. https://labelgrade.com/data

## Updates

Regenerated as the catalog grows and pages are re-verified against USDA. Check the `meta` block in any JSON file for the current version and generation date.

---

Built and maintained by **[Labelgrade](https://labelgrade.com)**. Questions or corrections: open an issue, or see [labelgrade.com/corrections](https://labelgrade.com/corrections).
