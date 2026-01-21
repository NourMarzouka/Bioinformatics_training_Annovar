# 04 — Interpret Results (Startup Guide Outputs)

This section explains how to read the annotated output from the startup guide workflow.

## Learning goals
- Find key columns in the output file.
- Understand what “gene” and “function” mean in context.
- Export a simple table for sharing.

---

## Step 1: Open the main results file

```bash
cd ~/annovar_training
head -n 3 example.hg19_refGene.variant_function
```

**Explanation:**
- The first line is the header (column names).
- The next lines are your annotated variants.

---

## Step 2: Important columns to notice

In the header, look for:

- **Func.refGene**: Where the variant is (exonic, intronic, etc.).
- **Gene.refGene**: The gene name.
- **ExonicFunc.refGene**: If exonic, what type of change (missense, synonymous, etc.).

> ✅ You don’t need to know every column now. Focus on the ones above.

---

## Step 3: Export a simpler table

To make a smaller table with only a few columns:

```bash
cut -f1,2,3,4,5 example.hg19_refGene.variant_function > example_simple.tsv
```

**Explanation:**
- `cut -f` selects specific columns by number.
- The output is saved in `example_simple.tsv`.

Check the file:

```bash
head -n 3 example_simple.tsv
```

---

## Step 4: (Optional) Open in a spreadsheet

You can open `example_simple.tsv` in Excel or Google Sheets for easier viewing.

---

## Checkpoint ✅

You are ready to proceed if:
- You can identify the gene name column.
- You created a simplified table.
