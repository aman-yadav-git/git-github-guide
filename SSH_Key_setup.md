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
