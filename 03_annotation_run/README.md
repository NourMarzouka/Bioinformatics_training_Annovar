# 03 — Run Annotation (Following the Startup Guide)

In this section, you will run ANNOVAR on a tiny example VCF file using the **official startup workflow**.

Startup guide reference:
https://annovar.openbioinformatics.org/en/latest/user-guide/startup/

## Learning goals
- Convert a VCF into ANNOVAR input format.
- Annotate using `annotate_variation.pl` as shown in the startup guide.
- Generate output files you can inspect.

---

## Step 1: Copy the example VCF

We include a tiny VCF in `assets/`.

```bash
cd ~/annovar_training
cp /path/to/repo/assets/example.vcf .
```

**Explanation:**
- Replace `/path/to/repo` with the path to this repository.
- `cp` copies the file into your working folder.

> ✅ After this, you should see `example.vcf` in `~/annovar_training`.

---

## Step 2: Convert VCF to ANNOVAR input

```bash
cd ~/annovar_training

perl ~/annovar_training/tools/annovar/convert2annovar.pl \
  -format vcf4 \
  example.vcf > example.avinput
```

**Explanation:**
- ANNOVAR expects a special input format called **avinput**.
- This command converts your VCF to that format.
- The output is saved as `example.avinput`.

---

## Step 3: Run annotation with the startup guide method

The startup guide uses `annotate_variation.pl` with `-filter` for additional databases.

```bash
cd ~/annovar_training

perl ~/annovar_training/tools/annovar/annotate_variation.pl \
  -out example \
  -build hg19 \
  -dbtype refGene \
  example.avinput \
  ~/annovar_training/tools/annovar/humandb/

perl ~/annovar_training/tools/annovar/annotate_variation.pl \
  -filter \
  -dbtype cytoBand \
  -build hg19 \
  -out example \
  example.avinput \
  ~/annovar_training/tools/annovar/humandb/

perl ~/annovar_training/tools/annovar/annotate_variation.pl \
  -filter \
  -dbtype genomicSuperDups \
  -build hg19 \
  -out example \
  example.avinput \
  ~/annovar_training/tools/annovar/humandb/
```

**Explanation (simple):**
- The first command annotates genes using **refGene**.
- The next two commands add extra context using **cytoBand** and **genomicSuperDups**.
- Each command reads `example.avinput` and writes output files named `example.*`.

---

## Step 4: Check your outputs

After running the commands, you should see files like:

```
example.hg19_refGene.variant_function
example.hg19_refGene.exonic_variant_function
example.hg19_cytoBand_dropped
example.hg19_genomicSuperDups_dropped
```

View a few lines:

```bash
head -n 5 example.hg19_refGene.variant_function
```

**Explanation:**
- This file contains your annotated variants with gene information.
- We only view the first 5 lines to keep it simple.

---

## Checkpoint ✅

You are ready to proceed if:
- `example.avinput` was created.
- You see `example.hg19_refGene.variant_function`.
- You can open the output and see annotation columns.
