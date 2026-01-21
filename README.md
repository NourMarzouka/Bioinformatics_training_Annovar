# Bioinformatics Training: VCF Annotation with ANNOVAR

Welcome! This repository is a **step-by-step, beginner-friendly tutorial** for students with no prior background in coding or bioinformatics.

By the end, you will be able to take a small VCF file and annotate it using ANNOVAR.

---

## Quick start (copy & paste)

> If you already installed tools, you can follow this quick run first.

```bash
# 1) Go to your training folder
cd ~/annovar_training

# 2) Copy the example data from this repo
cp /path/to/repo/assets/example.vcf .

# 3) Convert VCF to ANNOVAR input
perl ~/annovar_training/tools/annovar/convert2annovar.pl \
  -format vcf4 \
  example.vcf > example.avinput

# 4) Run annotation
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

# 5) View results
head -n 5 example.hg19_multianno.txt
```

**Explanation:**
- Replace `/path/to/repo` with the actual path to this repo on your computer.
- If you have not installed ANNOVAR or its databases, start at `00_prerequisites`.

---

## Repository map (follow in order)

1. **00_prerequisites/** — How to open a terminal and install tools.
2. **01_data_intro/** — What a VCF is and why annotation matters.
3. **02_annovar_setup/** — Download and set up ANNOVAR + databases.
4. **03_annotation_run/** — Convert and annotate a VCF step-by-step.
5. **04_results_interpretation/** — Read and simplify the results.
6. **05_practice/** — Practice exercises and troubleshooting.
7. **assets/** — Example data used in the lessons.

---

## Learning goals

By the end of this tutorial you will:
- Understand the basics of VCF files.
- Run ANNOVAR annotation on a small dataset.
- Interpret the main results and export a simple table.

---

## Requirements

- Basic terminal access (macOS Terminal, Linux Terminal, or Windows WSL)
- Tools: `perl`, `wget` or `curl`, and `unzip`

---

## Need help?

Each lesson includes:
- Plain-language explanations.
- Commands you can copy and paste.
- Checkpoints to confirm you are on track.

Start at **00_prerequisites** if you are brand new.
