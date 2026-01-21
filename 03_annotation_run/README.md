# 03 — Run Annotation (Step-by-Step)

In this section, you will run ANNOVAR on a tiny example VCF file.

## Learning goals
- Convert a VCF into ANNOVAR input format.
- Run an annotation command.
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

## Step 3: Run table annotation

```bash
perl ~/annovar_training/tools/annovar/table_annovar.pl \
  example.avinput \
  ~/annovar_training/tools/annovar/humandb/ \
  -buildver hg19 \
  -out example \
  -remove \
  -protocol refGene,gnomad211_genome \
  -operation g,f \
  -nastring . \
  -polish
```

**Explanation (line by line):**
- `example.avinput` is your input.
- `humandb/` points to the database folder.
- `-buildver hg19` chooses the genome build.
- `-out example` names the output files.
- `-protocol` lists the databases to use.
- `-operation g,f` tells ANNOVAR how to apply each database.
- `-nastring .` uses `.` for missing values.
- `-polish` makes the output nicer to read.

---

## Step 4: Check your outputs

After running the command, you should see files like:

```
example.hg19_multianno.txt
example.hg19_multianno.vcf
```

View the text output:

```bash
head -n 5 example.hg19_multianno.txt
```

**Explanation:**
- This file contains your annotated variants in a table.
- We only view the first 5 lines to keep it simple.

---

## Checkpoint ✅

You are ready to proceed if:
- `example.avinput` was created.
- `example.hg19_multianno.txt` exists.
- You can open the output and see annotation columns.
