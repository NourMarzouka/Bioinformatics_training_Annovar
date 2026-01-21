# 05 — Practice and Checkpoints

This section gives simple exercises so students can practice.

## Practice 1: Verify your tools

Run these commands and confirm they work:

```bash
perl -v
wget --version
unzip -v
```

**What this checks:**
- You have Perl and download/unzip tools installed.

---

## Practice 2: Explore the VCF

```bash
cd ~/annovar_training
wc -l example.vcf
```

**Explanation:**
- `wc -l` counts the number of lines in the file.
- This gives you a sense of file size.

---

## Practice 3: Re-run annotation

Repeat the annotation command from the previous lesson and confirm the output files are re-created.

---

## Troubleshooting: Common errors

### 1) “command not found”
- Make sure ANNOVAR is unpacked and the path is correct.
- Use the full path to scripts (as shown in lessons).

### 2) “No such file or directory”
- Check your current folder with `pwd`.
- List files with `ls` to verify names.

### 3) Download issues
- Check your internet connection.
- Try running the download command again.

---

## Final checklist ✅

You are finished if:
- You can run annotation without errors.
- You can explain what gene a variant maps to.
- You can export a simplified table.
