# git-github-guide
Git & GitHub Complete Guide

---
## Create a GitHub Account 

**If you already have an account, skip to Section 02.**
1. Open https://github.com in your browser.
2. Click Sign up and enter your email, password, and a username.
3. Verify your email address — GitHub sends a confirmation link.
4. On the welcome screen you can skip the survey and go straight to your dashboard.

> [!TIP]
>Pick a clean professional username — it will appear in all your repo URLs and on your profile README. e.g. github.com/yourusername


**Install Git on Fedora**
```
sudo dnf install git -y
```

**Verify installation**
```
git --version
```
> Expected: git version 2.x.x


## Set your identity (one-time setup)

> Git attaches your name and email to every commit.
```
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

> Set default branch name to main
```
git config --global init.defaultBranch main
```

> Verify
```
git config --list
```

## SSH Key Setup


**GitHub no longer accepts passwords over HTTPS. SSH keys are the cleanest solution — you set them up
once and never type credentials again.**

### Step 1 — Generate the key
```
ssh-keygen -t ed25519 -C "your@email.com"
```
- Press Enter for all prompts (default path, no passphrase is fine for local dev)


### Step 2 — Copy your public key
```
cat ~/.ssh/id_ed25519.pub
```
> Copy the entire output — starts with: ssh-ed25519 AAAA...


### Step 3 — Add key to GitHub


1.  Go to `github.com` → `Settings` → `SSH and GPG keys`
2.  Click `New SSH key`
3.  Give it a title (e.g. "Fedora laptop") and paste your key
4.  Click `Add SSH key`


### Step 4 — add config

```
cd ~/.ssh
vim config
```
Add this line
```
Host github.com
user git
IdentityFile ~/.ssh/id_ed25519_git
IdentitiesOnly yes
```


### Step 5 — Test the connection

```
ssh -T git@github.com
```
> Expected: Hi yourusername! You've successfully authenticated...


> [!NOTE]
> If you prefer HTTPS instead of SSH, generate a Personal Access Token at GitHub → Settings →
Developer settings → Personal access tokens. Use it as your password when Git prompts for
credentials.


## Create a Repository on GitHub 

**1. Click the + icon (top-right)** → `New repository`

**2. Fill in:**

- Repository name Devops (or any name you want)
- Description Optional — short one-liner about this repo
- Visibility Public (visible to all) or Private (only you)
- Initialize Leave all checkboxes UNCHECKED — you have local files already

**3. Click Create repository**

**4. Copy the SSH URL shown — looks like:** `git@github.com:yourusername/Devops.git`


## Write a README.md 


A `README.md` is the first thing people see when they visit your repo. GitHub renders Markdown
automatically.


## Create the file inside your folder
```
cd ~/Devops
vim README.md
```
---

## Push Your Folder & file to GitHub
 
**Run these commands from your home directory (~) so that the folder & file**
> initialize an existing directory as a Git repository
``
git init 
``
> show modified files in working directory, staged for your next commit
```
git status
```
> add a file as it looks now to your next commit (stage)
```
git add (file or folder)
```
> unstage a file while retaining the changes in working directory
```
git reset (file or folder)
```
> diff of what is changed but not staged
```
git diff
```
> diff of what is staged but not yet commited
```
git diff --staged
```
> commit your staged content as a new commit snapshot
```
git commit -m “[descriptive message]”
```







































