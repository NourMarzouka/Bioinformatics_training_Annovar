# 01 — VCF Basics (What You Are Annotating)

This section explains what a VCF file is in plain language.

## Learning goals
- Know what a VCF file represents.
- Recognize the main columns in a VCF file.
- Understand why annotation matters.

---

## What is a VCF?

A **VCF (Variant Call Format)** file is a text file that stores genetic changes (variants) found in a sample. Each line typically represents one variant.

Think of it like a spreadsheet where each row is a variant and each column is a piece of information about it.

---

## The main columns in a VCF

Here is an example line (we will use a toy file later):

```
chr1	879317	.	G	A	.	PASS	.
```

| Column | Name   | Meaning (simple) |
|--------|--------|------------------|
| 1      | CHROM  | Chromosome name |
| 2      | POS    | Position (where the variant is) |
| 3      | ID     | Variant ID (often blank) |
| 4      | REF    | Reference base (what is expected) |
| 5      | ALT    | Alternate base (what is observed) |
| 6      | QUAL   | Quality score |
| 7      | FILTER | Whether it passed filters |
| 8      | INFO   | Extra information |

> ✅ You do not need to memorize this yet. The key idea is that **a VCF line describes a single variant**.

---

## Why do we annotate a VCF?

A raw VCF tells us **what changed**, but not **what it means**.

Annotation adds helpful context, like:
- Which gene is affected?
- Is the change in a coding region?
- Is the change common or rare?

ANNOVAR is the tool we use to add this context.

---

## Mini practice (view a sample VCF)

We will add a small sample VCF file in the `assets/` folder. You can view it later using:

```bash
head -n 5 ../assets/example.vcf
```

**Explanation:**
- `head -n 5` shows only the first 5 lines.
- This is a safe way to peek at a file without opening it in a text editor.

---

## Checkpoint ✅

You are ready to proceed if:
- You understand that each VCF line is a variant.
- You know annotation adds meaning to raw variants.
