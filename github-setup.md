# GitHub Account and Git Setup Guide

This guide explains how to create a GitHub account and configure Git on both Windows and macOS devices. It is written for beginners who want to use GitHub for coding projects, learning full stack development, and sharing code online.

## Docs Menu

- [English: GitHub Account and Git Setup Guide](github-setup.md)
- [ភាសាខ្មែរ: មគ្គុទ្ទេសក៍បង្កើត GitHub និងរៀបចំ Git](github-setup-km.md)

## 1. What You Are Setting Up

You will set up four things:

1. A GitHub account
2. Git on your computer
3. A secure connection between your computer and GitHub
4. A first test repository to confirm everything works

Git is the tool that tracks code changes on your computer.

GitHub is the online service where you store, back up, and share Git repositories.

### How Git and GitHub Work Together

Think of your project in three places:

1. **Working folder**: the files you edit on your computer.
2. **Local Git repository**: the saved history on your computer.
3. **GitHub repository**: the online copy stored in your GitHub account.

The normal workflow is:

```text
edit files -> git add -> git commit -> git push
```

Meaning:

- `git add` chooses which changes you want to save.
- `git commit` saves those changes into Git history on your computer.
- `git push` uploads your commits to GitHub.
- `git pull` downloads new commits from GitHub to your computer.

Important: GitHub is not the same thing as Git. Git can work without GitHub, but GitHub needs Git repositories.

### Words You Should Know First

| Word | Meaning |
| --- | --- |
| Repository | A project folder tracked by Git |
| Commit | A saved version of your changes |
| Branch | A separate line of work in the same repository |
| Remote | The online repository address, usually GitHub |
| Clone | Download a GitHub repository to your computer |
| Push | Upload your commits to GitHub |
| Pull | Download the newest commits from GitHub |
| Stage | Select files for the next commit |

## 2. Create a GitHub Account

1. Open this website:

   ```text
   https://github.com
   ```

2. Click **Sign up**.

3. Enter your email address.

4. Create a strong password.

5. Choose a username.

   Example:

   ```text
   yourname-dev
   yourname-code
   senghong-fullstack
   ```

6. Verify your email address.

7. Complete any GitHub account setup questions.

8. After signing in, open:

   ```text
   https://github.com/settings/profile
   ```

9. Add your basic profile information:

   - Name
   - Profile picture
   - Short bio
   - Location, if you want
   - Website or portfolio link, if you have one

## 3. Recommended GitHub Account Security

Before using GitHub seriously, enable two-factor authentication.

1. Open:

   ```text
   https://github.com/settings/security
   ```

2. Find **Two-factor authentication**.

3. Click **Enable two-factor authentication**.

4. Choose an authenticator app, such as:

   - Google Authenticator
   - Microsoft Authenticator
   - Authy
   - 1Password

5. Save your recovery codes somewhere safe.

Do not store recovery codes only on the same computer. If you lose access to your device, you may need those codes to recover your GitHub account.

## 4. Install Git on Windows

### Option A: Install Git for Windows

1. Open:

   ```text
   https://git-scm.com/download/win
   ```

2. Download the installer.

3. Run the installer.

4. During installation, these options are recommended:

   - Editor: **Visual Studio Code**, if installed
   - Default branch name: **main**
   - PATH environment: **Git from the command line and also from 3rd-party software**
   - HTTPS transport backend: **Use the native Windows Secure Channel library**
   - Line endings: **Checkout Windows-style, commit Unix-style line endings**
   - Terminal emulator: **Use MinTTY**
   - Credential helper: **Git Credential Manager**

5. Finish the installation.

6. Open **Git Bash** from the Start Menu.

7. Check Git version:

   ```bash
   git --version
   ```

You should see output similar to:

```text
git version 2.xx.x
```

### Option B: Install Git with winget

If your Windows device has `winget`, open PowerShell and run:

```powershell
winget install --id Git.Git -e --source winget
```

After installation, close and reopen PowerShell, then check:

```powershell
git --version
```

## 5. Install Git on macOS

### Option A: Install Git with Xcode Command Line Tools

Open Terminal and run:

```bash
git --version
```

If Git is not installed, macOS may ask you to install the Xcode Command Line Tools. Click **Install** and wait for it to finish.

Then check again:

```bash
git --version
```

### Option B: Install Git with Homebrew

If you use Homebrew, run:

```bash
brew install git
```

Then check:

```bash
git --version
```

If Homebrew is not installed, you can install it from:

```text
https://brew.sh
```

## 6. Configure Git Identity

Git needs your name and email address. This information appears in your commits.

Use the same email address that you used for GitHub, or use your GitHub private no-reply email.

### Windows

Open Git Bash or PowerShell:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main
```

Example:

```bash
git config --global user.name "Senghong"
git config --global user.email "senghong@example.com"
git config --global init.defaultBranch main
```

### macOS

Open Terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main
```

Example:

```bash
git config --global user.name "Senghong"
git config --global user.email "senghong@example.com"
git config --global init.defaultBranch main
```

### Verify Your Git Config

Run:

```bash
git config --global --list
```

You should see something like:

```text
user.name=Your Name
user.email=your-email@example.com
init.defaultbranch=main
```

## 7. Choose HTTPS or SSH

There are two common ways to connect your computer to GitHub:

| Method | Best For | Notes |
| --- | --- | --- |
| HTTPS | Beginners and simple setup | GitHub may ask you to sign in through the browser or Git Credential Manager |
| SSH | Daily development | More convenient after setup because you do not enter credentials repeatedly |

Recommended setup:

- Beginners can start with HTTPS.
- Developers who push code often should set up SSH.

## 8. HTTPS Setup

HTTPS usually works automatically after Git is installed.

When you push code to GitHub for the first time, Git may open a browser window and ask you to sign in. After you sign in, Git Credential Manager saves your login securely.

### Test HTTPS Later

You will test HTTPS when creating your first repository.

HTTPS repository URLs look like this:

```text
https://github.com/username/repository-name.git
```

## 9. SSH Setup on Windows

Use this section if you want to connect with SSH.

### Check for Existing SSH Keys

Open Git Bash:

```bash
ls -al ~/.ssh
```

Look for files like:

```text
id_ed25519
id_ed25519.pub
id_rsa
id_rsa.pub
```

If you already have `id_ed25519.pub`, you can use it. If not, create a new key.

### Create a New SSH Key

Replace the email with your GitHub email:

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

When asked where to save the key, press **Enter** to accept the default location.

When asked for a passphrase, you can enter a secure passphrase or press **Enter** to skip it.

Recommended: use a passphrase for better security.

### Start the SSH Agent

In Git Bash:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### Copy Your Public SSH Key

In Git Bash:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the full output. It starts with `ssh-ed25519` and ends with your email address.

### Add SSH Key to GitHub

1. Open:

   ```text
   https://github.com/settings/keys
   ```

2. Click **New SSH key**.

3. Add a title, for example:

   ```text
   Windows Laptop
   ```

4. Paste your public key.

5. Click **Add SSH key**.

### Test SSH Connection

In Git Bash:

```bash
ssh -T git@github.com
```

The first time, type:

```text
yes
```

If successful, GitHub will show a message like:

```text
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

## 10. SSH Setup on macOS

Use this section if you want to connect with SSH.

### Check for Existing SSH Keys

Open Terminal:

```bash
ls -al ~/.ssh
```

Look for files like:

```text
id_ed25519
id_ed25519.pub
id_rsa
id_rsa.pub
```

If you already have `id_ed25519.pub`, you can use it. If not, create a new key.

### Create a New SSH Key

Replace the email with your GitHub email:

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

When asked where to save the key, press **Enter** to accept the default location.

When asked for a passphrase, you can enter a secure passphrase or press **Enter** to skip it.

Recommended: use a passphrase for better security.

### Start the SSH Agent

Run:

```bash
eval "$(ssh-agent -s)"
```

### Add SSH Key to macOS Keychain

Create or edit the SSH config file:

```bash
open ~/.ssh/config
```

If the file does not exist, create it:

```bash
touch ~/.ssh/config
open ~/.ssh/config
```

Add this content:

```text
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

Then run:

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

If `--apple-use-keychain` does not work on your macOS version, try:

```bash
ssh-add -K ~/.ssh/id_ed25519
```

### Copy Your Public SSH Key

Run:

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

This copies the key to your clipboard.

You can also display it:

```bash
cat ~/.ssh/id_ed25519.pub
```

### Add SSH Key to GitHub

1. Open:

   ```text
   https://github.com/settings/keys
   ```

2. Click **New SSH key**.

3. Add a title, for example:

   ```text
   MacBook
   ```

4. Paste your public key.

5. Click **Add SSH key**.

### Test SSH Connection

Run:

```bash
ssh -T git@github.com
```

The first time, type:

```text
yes
```

If successful, GitHub will show a message like:

```text
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

## 11. Install Visual Studio Code

Visual Studio Code is a popular code editor for full stack development.

Download it from:

```text
https://code.visualstudio.com
```

Recommended extensions:

- GitHub Pull Requests
- GitLens
- Prettier
- ESLint
- JavaScript and TypeScript Nightly, optional
- Tailwind CSS IntelliSense, if you use Tailwind CSS

After installing VS Code, open a terminal and check whether the `code` command works:

```bash
code --version
```

If it does not work on macOS:

1. Open VS Code.
2. Press `Command + Shift + P`.
3. Search for **Shell Command: Install 'code' command in PATH**.
4. Press Enter.

On Windows, the VS Code installer usually includes an option called **Add to PATH**. Enable it during installation.

## 12. Optional: Install GitHub CLI

GitHub CLI lets you use GitHub from the terminal with the `gh` command.

### Windows

Using winget:

```powershell
winget install --id GitHub.cli
```

Check:

```powershell
gh --version
```

Login:

```powershell
gh auth login
```

### macOS

Using Homebrew:

```bash
brew install gh
```

Check:

```bash
gh --version
```

Login:

```bash
gh auth login
```

Recommended login choices:

- GitHub.com
- HTTPS or SSH, depending on your setup
- Login with browser

## 13. Create Your First GitHub Repository

### Create the Repository on GitHub

1. Open:

   ```text
   https://github.com/new
   ```

2. Repository name:

   ```text
   hello-github
   ```

3. Description:

   ```text
   My first GitHub repository
   ```

4. Choose **Public** or **Private**.

5. Check **Add a README file**.

6. Click **Create repository**.

## 14. Clone the Repository to Your Computer

Open the repository page on GitHub and click **Code**.

Choose either HTTPS or SSH.

### Clone with HTTPS

Repository URL example:

```text
https://github.com/username/hello-github.git
```

Command:

```bash
git clone https://github.com/username/hello-github.git
```

### Clone with SSH

Repository URL example:

```text
git@github.com:username/hello-github.git
```

Command:

```bash
git clone git@github.com:username/hello-github.git
```

### Enter the Project Folder

```bash
cd hello-github
```

Open it in VS Code:

```bash
code .
```

## 15. Make Your First Commit

Inside the repository folder, create a file named `notes.md`.

Add this content:

```markdown
# My GitHub Notes

Today I learned how to set up Git and GitHub.
```

Check the repository status:

```bash
git status
```

Stage the file:

```bash
git add notes.md
```

Commit the change:

```bash
git commit -m "Add GitHub setup notes"
```

Push it to GitHub:

```bash
git push
```

Refresh your GitHub repository page. You should see the new `notes.md` file online.

## 16. Common Daily Git Commands

### Check Status

```bash
git status
```

Shows changed files.

### Get Latest Code

```bash
git pull
```

Downloads the latest changes from GitHub.

### Stage Files

```bash
git add filename
```

Stage one file.

```bash
git add .
```

Stage all changed files in the current folder.

### Commit Changes

```bash
git commit -m "Write a clear commit message"
```

Saves a snapshot of your changes locally.

### Push Changes

```bash
git push
```

Uploads your commits to GitHub.

### See Commit History

```bash
git log --oneline
```

Shows recent commits.

### Check Remote Repository

```bash
git remote -v
```

Shows where your local repository pushes and pulls code.

### Create a Branch

```bash
git switch -c feature-name
```

Creates a new branch and moves you to it.

Branch names should be short and clear:

```text
add-login-page
fix-navbar-spacing
update-readme
```

### Switch Branches

```bash
git switch main
```

Moves you back to the `main` branch.

### See Changed Lines

```bash
git diff
```

Shows the exact file changes that are not committed yet.

## 17. Recommended Folder Structure

Keep your coding projects in one main folder.

### Windows Example

```text
C:\Users\YourName\Projects
```

Create it in PowerShell:

```powershell
mkdir "$HOME\Projects"
cd "$HOME\Projects"
```

### macOS Example

```text
/Users/YourName/Projects
```

Create it in Terminal:

```bash
mkdir -p ~/Projects
cd ~/Projects
```

Clone your repositories inside this folder.

## 18. GitHub Personal Access Tokens

GitHub no longer accepts account passwords for Git operations over HTTPS. If Git asks for a password in the terminal, you may need a personal access token instead.

Usually, Git Credential Manager handles this for you through browser login. Only create a token if a tool specifically asks for one.

To create a token:

1. Open:

   ```text
   https://github.com/settings/tokens
   ```

2. Choose **Fine-grained tokens**.

3. Click **Generate new token**.

4. Set repository access only to what you need.

5. Set permissions only to what you need.

6. Copy the token immediately.

Treat tokens like passwords. Do not paste them into code, screenshots, chat messages, or public repositories.

## 19. Configure GitHub Email Privacy

If you do not want your personal email shown in commits:

1. Open:

   ```text
   https://github.com/settings/emails
   ```

2. Enable:

   ```text
   Keep my email addresses private
   ```

3. Copy your GitHub no-reply email.

It looks similar to:

```text
12345678+username@users.noreply.github.com
```

Then configure Git:

```bash
git config --global user.email "12345678+username@users.noreply.github.com"
```

## 20. Troubleshooting

### Problem: `git` Is Not Recognized on Windows

Close and reopen PowerShell or Git Bash.

If it still does not work, reinstall Git and make sure this option is selected:

```text
Git from the command line and also from 3rd-party software
```

### Problem: Permission Denied with SSH

Run:

```bash
ssh -T git@github.com
```

If it fails, check:

- Your public key was added to GitHub.
- You copied the `.pub` file, not the private key.
- Your SSH agent is running.
- Your repository remote uses the SSH URL.

Check remote URL:

```bash
git remote -v
```

Change HTTPS remote to SSH:

```bash
git remote set-url origin git@github.com:username/repository-name.git
```

### Problem: Authentication Failed with HTTPS

Try signing in again through Git Credential Manager.

On Windows:

1. Open **Credential Manager**.
2. Go to **Windows Credentials**.
3. Remove old GitHub credentials.
4. Run `git push` again and sign in through the browser.

On macOS:

1. Open **Keychain Access**.
2. Search for `github`.
3. Remove old GitHub credentials if needed.
4. Run `git push` again and sign in.

### Problem: Wrong Name or Email in Commits

Check:

```bash
git config --global --list
```

Update:

```bash
git config --global user.name "Your Correct Name"
git config --global user.email "your-correct-email@example.com"
```

### Problem: Push Rejected

First get the latest version from GitHub:

```bash
git pull
```

Then push again:

```bash
git push
```

If Git reports a conflict, open the files mentioned in the error, fix the conflicting lines, then run:

```bash
git add .
git commit -m "Resolve merge conflict"
git push
```

### Problem: You Added the Wrong File Before Commit

If you ran `git add` but have not committed yet, unstage the file:

```bash
git restore --staged filename
```

Example:

```bash
git restore --staged notes.md
```

This does not delete the file. It only removes the file from the next commit.

### Problem: You Changed a File and Want to Discard the Change

Use this only when you are sure you do not need the change:

```bash
git restore filename
```

Example:

```bash
git restore notes.md
```

This brings the file back to the last committed version.

## 21. Final Setup Checklist

Use this checklist to confirm your setup is complete.

- [ ] GitHub account created
- [ ] Email verified
- [ ] Two-factor authentication enabled
- [ ] Git installed
- [ ] Git name configured
- [ ] Git email configured
- [ ] Default branch configured as `main`
- [ ] VS Code installed
- [ ] SSH key added to GitHub, optional but recommended
- [ ] `ssh -T git@github.com` works, if using SSH
- [ ] First repository created
- [ ] Repository cloned to computer
- [ ] First commit pushed to GitHub

## 22. Quick Command Reference

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main
git config --global --list
git clone repository-url
git status
git add .
git commit -m "Commit message"
git pull
git push
git log --oneline
```

## 23. Suggested Learning Flow

After setup, practice in this order:

1. Create a repository.
2. Clone it.
3. Add or edit a file.
4. Run `git status`.
5. Run `git add`.
6. Run `git commit`.
7. Run `git push`.
8. Check the result on GitHub.
9. Repeat until the workflow feels familiar.

## 24. Commit Message Examples

A good commit message says what changed. Keep it short, clear, and specific.

Good examples:

```text
Add homepage navigation
Fix login form validation
Update GitHub setup guide
Create student profile page
```

Avoid unclear messages:

```text
update
fix
changes
final
```

For beginners, this format is enough:

```text
Action + what changed
```

Examples:

- `Add contact form`
- `Fix image path`
- `Update README instructions`

## 25. What to Put in `.gitignore`

A `.gitignore` file tells Git which files should not be committed.

Common examples:

```gitignore
node_modules/
.env
.DS_Store
dist/
build/
```

Do not commit:

- Passwords
- API keys
- Secret tokens
- Large dependency folders such as `node_modules`
- Temporary build output

For a basic JavaScript project, create `.gitignore` in the project root:

```text
node_modules/
.env
.DS_Store
```

Then check:

```bash
git status
```

Git should no longer show ignored files.

## 26. Simple Practice Exercise

Use this exercise to confirm that you understand the full flow:

1. Create a repository named `practice-git`.
2. Clone it to your computer.
3. Create `index.html`.
4. Add a heading inside the file.
5. Run `git status`.
6. Run `git add index.html`.
7. Run `git commit -m "Add first HTML page"`.
8. Run `git push`.
9. Open GitHub and confirm that `index.html` is visible.

Then practice one more change:

1. Edit `index.html`.
2. Run `git diff`.
3. Run `git add .`.
4. Run `git commit -m "Update homepage content"`.
5. Run `git push`.

## 27. Khmer Version

A Khmer starter version is available here:

[មគ្គុទ្ទេសក៍បង្កើត GitHub និងរៀបចំ Git ជាភាសាខ្មែរ](github-setup-km.md)
