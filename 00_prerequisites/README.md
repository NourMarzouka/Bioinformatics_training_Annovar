# 00 — Prerequisites (Very Beginner Friendly)

This section helps you get ready to run commands in a terminal. **If you have never used a terminal before, start here.**

## Learning goals
- Open a terminal and run simple commands safely.
- Install the small tools needed for the tutorial.
- Know where your files live.

---

## Step 1: Open a terminal

**macOS**: Press `Command + Space`, type **Terminal**, press Enter.

**Windows**: Open **PowerShell** (search “PowerShell” from the Start menu).

**Linux**: Open **Terminal** from your applications menu.

> ✅ You should see a window with a blinking cursor.

---

## Step 2: Learn 4 basic commands

These commands do not change anything. They only show information.

```bash
pwd
```
- **What it does**: Shows your **p**resent **w**orking **d**irectory (where you are).

```bash
ls
```
- **What it does**: Lists files and folders in your current location.

```bash
cd ~
```
- **What it does**: Moves you to your home folder (a safe place to work).

```bash
mkdir annovar_training
```
- **What it does**: Creates a new folder named `annovar_training`.

> ✅ After `mkdir`, run `ls` and confirm you see the new folder.

---

## Step 3: Install required tools

We use three small tools:
- **wget** or **curl** (to download files)
- **unzip** (to unpack files)
- **perl** (ANNOVAR runs in Perl)

### macOS (Homebrew)
If you do not have Homebrew, install it from https://brew.sh/.

```bash
brew install wget unzip perl
```

### Ubuntu/Debian Linux
```bash
sudo apt-get update
sudo apt-get install -y wget unzip perl
```

### Windows (PowerShell)
We recommend using **Windows Subsystem for Linux (WSL)** for this tutorial.
Follow Microsoft’s guide: https://learn.microsoft.com/windows/wsl/install

Then use the Ubuntu/Debian commands above inside WSL.

---

## Step 4: Create your working folder

We will work in one folder for everything.

```bash
cd ~
mkdir -p annovar_training
cd annovar_training
```

> ✅ You should now be inside `~/annovar_training`. Confirm with `pwd`.

---

## Step 5: Quick glossary

- **Terminal**: A window where you type commands.
- **Command**: A line of text that tells your computer to do something.
- **Directory**: Another word for a folder.
- **VCF**: A file format that stores genetic variants.

---

## Checkpoint ✅

You are ready to proceed if:
- You can run `pwd` and `ls` without errors.
- You have a folder called `annovar_training` in your home folder.
- You installed `wget`/`curl`, `unzip`, and `perl`.

If you are stuck, ask the instructor or check the “Common errors” section in later lessons.
