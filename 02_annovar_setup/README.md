# 02 — Install and Set Up ANNOVAR

This section shows how to download ANNOVAR and its databases.

> **Important:** ANNOVAR is free for academic use but requires registration.
> You must create an account and download the software from the official site:
> https://annovar.openbioinformatics.org/en/latest/user-guide/download/

## Learning goals
- Download ANNOVAR.
- Place it in your training folder.
- Download the required annotation databases.

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

## Step 4: Add ANNOVAR to your PATH (optional but helpful)

This lets you run ANNOVAR commands from anywhere.

```bash
export PATH="$HOME/annovar_training/tools/annovar:$PATH"
```

**Explanation:**
- This only lasts for your current terminal session.
- We use `$HOME` so the path works on any computer.

---

## Step 5: Download annotation databases

ANNOVAR provides scripts to download databases. We will use two common ones:
- **refGene** (gene annotations)
- **gnomAD** (population frequencies)

```bash
cd ~/annovar_training/tools/annovar
mkdir -p humandb

perl annotate_variation.pl -buildver hg19 -downdb -webfrom annovar refGene humandb/
perl annotate_variation.pl -buildver hg19 -downdb -webfrom annovar gnomad211_genome humandb/
```

**Explanation:**
- `-buildver hg19` chooses the genome build (common for training).
- `humandb/` is where databases are stored.

> ✅ These downloads may take time depending on your internet speed.

---

## Checkpoint ✅

You are ready to proceed if:
- You see the `annovar/` folder in `~/annovar_training/tools`.
- You have a `humandb/` folder inside ANNOVAR.
- The database files downloaded without errors.
