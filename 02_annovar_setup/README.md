# 02 — Install and Set Up ANNOVAR (Following the Official Startup Guide)

This section follows the official ANNOVAR **Startup** instructions:
https://annovar.openbioinformatics.org/en/latest/user-guide/startup/

> **Important:** ANNOVAR is free for academic use but requires registration.
> You must create an account and download the software from the official site:
> https://annovar.openbioinformatics.org/en/latest/user-guide/download/

## Learning goals
- Download and unpack ANNOVAR.
- Confirm the scripts run.
- Download the required databases.

---

## Step 1: Create a tools folder

Inside your training folder, create a place for tools:

```bash
cd ~/annovar_training
mkdir -p tools
```

**Explanation:**
- `mkdir -p` creates the folder if it doesn’t already exist.
- We keep tools separate from data.

---

## Step 2: Download ANNOVAR

After registering, download the ANNOVAR package (you will receive a link).

Move the downloaded file into `~/annovar_training/tools/`.

Example (your filename may differ):

```bash
mv ~/Downloads/annovar.latest.tar.gz ~/annovar_training/tools/
```

**Explanation:**
- `mv` moves the file into the tools folder.

---

## Step 3: Unpack ANNOVAR

```bash
cd ~/annovar_training/tools

tar -xvzf annovar.latest.tar.gz
```

**Explanation:**
- `tar -xvzf` unpacks the compressed archive.

You should now see a folder like `annovar/`.

---

## Step 4: Test that ANNOVAR runs

The startup guide suggests running a script to confirm ANNOVAR works:

```bash
cd ~/annovar_training/tools/annovar
perl annotate_variation.pl -help | head -n 5
```

**Explanation:**
- This prints a short help message and confirms Perl can run the script.
- `head -n 5` keeps the output short and readable.

---

## Step 5: Download annotation databases (as in the startup guide)

ANNOVAR provides scripts to download databases. The startup guide uses:
- **refGene** (gene annotations)
- **cytoBand** (chromosome banding)
- **genomicSuperDups** (segmental duplications)

```bash
cd ~/annovar_training/tools/annovar
mkdir -p humandb

perl annotate_variation.pl -buildver hg19 -downdb -webfrom annovar refGene humandb/
perl annotate_variation.pl -buildver hg19 -downdb -webfrom annovar cytoBand humandb/
perl annotate_variation.pl -buildver hg19 -downdb -webfrom annovar genomicSuperDups humandb/
```

**Explanation:**
- `-buildver hg19` chooses the genome build (used in the startup guide).
- `humandb/` is where databases are stored.

> ✅ These downloads may take time depending on your internet speed.

---

## Checkpoint ✅

You are ready to proceed if:
- You see the `annovar/` folder in `~/annovar_training/tools`.
- You can run `annotate_variation.pl -help` without errors.
- You have a `humandb/` folder with downloaded database files.
