# មគ្គុទ្ទេសក៍បង្កើត GitHub និងរៀបចំ Git

ឯកសារនេះសម្រាប់អ្នកចាប់ផ្តើមរៀន Full Stack Development។ វាពន្យល់ពីរបៀបបង្កើតគណនី GitHub ដំឡើង Git និងសាកល្បងបញ្ជូនកូដទៅ GitHub ជាជំហានៗ។

បើអ្នកចង់មើលអត្ថបទលម្អិតជាភាសាអង់គ្លេស សូមមើល [GitHub Account and Git Setup Guide](github-setup.md)។

## Docs Menu

- [ភាសាខ្មែរ: មគ្គុទ្ទេសក៍បង្កើត GitHub និងរៀបចំ Git](github-setup-km.md)
- [English: GitHub Account and Git Setup Guide](github-setup.md)

## 1. អ្វីដែលអ្នកនឹងរៀបចំ

អ្នកនឹងរៀបចំ 4 ចំណុចសំខាន់៖

1. គណនី GitHub
2. កម្មវិធី Git នៅលើកុំព្យូទ័រ
3. ការភ្ជាប់ពីកុំព្យូទ័រទៅ GitHub
4. Repository សាកល្បងដំបូង

**Git** គឺជាឧបករណ៍សម្រាប់រក្សាប្រវត្តិការកែប្រែកូដ។

**GitHub** គឺជាសេវាកម្មអនឡាញសម្រាប់រក្សាទុក បម្រុងទុក និងចែករំលែក Git repository។

Workflow ធម្មតា៖

```text
កែប្រែឯកសារ -> git add -> git commit -> git push
```

ន័យរបស់ command សំខាន់ៗ៖

- `git add` ជ្រើសរើសឯកសារដែលចង់រក្សាទុកក្នុង commit បន្ទាប់។
- `git commit` រក្សាទុកការកែប្រែជាប្រវត្តិនៅលើកុំព្យូទ័រ។
- `git push` ផ្ញើ commit ទៅ GitHub។
- `git pull` ទាញយក commit ថ្មីពី GitHub មកកុំព្យូទ័រ។

## 2. ពាក្យសំខាន់ៗ

| ពាក្យ | ន័យ |
| --- | --- |
| Repository | Project folder ដែល Git តាមដាន |
| Commit | កំណែដែលបានរក្សាទុក |
| Branch | ខ្សែការងារផ្សេងមួយនៅក្នុង repository |
| Remote | អាសយដ្ឋាន repository អនឡាញ |
| Clone | ទាញយក repository ពី GitHub មកកុំព្យូទ័រ |
| Push | ផ្ញើ commit ទៅ GitHub |
| Pull | ទាញយក commit ថ្មីពី GitHub |
| Stage | ជ្រើសរើស file សម្រាប់ commit បន្ទាប់ |

## 3. បង្កើតគណនី GitHub

1. បើក website:

   ```text
   https://github.com
   ```

2. ចុច **Sign up**។
3. បញ្ចូល email។
4. បង្កើត password ដែលខ្លាំង។
5. ជ្រើសរើស username។

   ឧទាហរណ៍៖

   ```text
   yourname-dev
   yourname-code
   senghong-fullstack
   ```

6. Verify email របស់អ្នក។
7. បន្ទាប់ពី login សូមបើក:

   ```text
   https://github.com/settings/profile
   ```

8. បំពេញ profile តាមតម្រូវការ៖

- Name
- Profile picture
- Short bio
- Location
- Website ឬ portfolio link បើមាន

## 4. បើក Two-Factor Authentication

Two-factor authentication ជួយការពារគណនី GitHub របស់អ្នក។

1. បើក:

   ```text
   https://github.com/settings/security
   ```

2. ស្វែងរក **Two-factor authentication**។
3. ចុច **Enable two-factor authentication**។
4. ជ្រើសរើស app ដូចជា Google Authenticator ឬ Microsoft Authenticator។
5. រក្សាទុក recovery codes នៅកន្លែងមានសុវត្ថិភាព។

កុំរក្សាទុក recovery codes តែនៅលើកុំព្យូទ័រតែមួយ។ បើអ្នកបាត់បង់ device អ្នកអាចត្រូវការកូដទាំងនោះដើម្បីយកគណនីត្រឡប់មកវិញ។

## 5. ដំឡើង Git លើ Windows

1. បើក:

   ```text
   https://git-scm.com/download/win
   ```

2. Download installer។
3. Run installer។
4. ជម្រើសដែលណែនាំ៖

- Editor: **Visual Studio Code**
- Default branch name: **main**
- PATH environment: **Git from the command line and also from 3rd-party software**
- HTTPS transport backend: **Use the native Windows Secure Channel library**
- Credential helper: **Git Credential Manager**

5. បន្ទាប់ពីដំឡើងរួច បើក Git Bash។
6. ពិនិត្យ version:

   ```bash
   git --version
   ```

បើដំណើរការ អ្នកនឹងឃើញ output ប្រហែល៖

```text
git version 2.xx.x
```

## 6. ដំឡើង Git លើ macOS

បើក Terminal ហើយ run:

```bash
git --version
```

បើ Git មិនទាន់មាន macOS អាចសួរឱ្យដំឡើង Xcode Command Line Tools។ ចុច **Install** ហើយរង់ចាំឱ្យចប់។

បើអ្នកប្រើ Homebrew អាចដំឡើង Git ដូចនេះ៖

```bash
brew install git
```

បន្ទាប់មកពិនិត្យម្តងទៀត៖

```bash
git --version
```

## 7. Configure Git Identity

Git ត្រូវការឈ្មោះ និង email របស់អ្នកសម្រាប់ commit។

Run commands ខាងក្រោម៖

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main
```

ឧទាហរណ៍៖

```bash
git config --global user.name "Senghong"
git config --global user.email "senghong@example.com"
git config --global init.defaultBranch main
```

ពិនិត្យ config:

```bash
git config --global --list
```

អ្នកគួរឃើញ៖

```text
user.name=Senghong
user.email=senghong@example.com
init.defaultbranch=main
```

## 8. ជ្រើស HTTPS ឬ SSH

មានវិធីភ្ជាប់ទៅ GitHub ពីរក្នុងការប្រើប្រាស់ទូទៅ៖

| វិធី | សមស្របសម្រាប់ | កំណត់សម្គាល់ |
| --- | --- | --- |
| HTTPS | អ្នកចាប់ផ្តើម | GitHub អាចសួរឱ្យ sign in តាម browser |
| SSH | អ្នកប្រើ Git រៀងរាល់ថ្ងៃ | ងាយស្រួលបន្ទាប់ពីរៀបចំរួច |

សម្រាប់អ្នកចាប់ផ្តើម អាចចាប់ផ្តើមដោយ HTTPS មុន។ បើអ្នក push code ជាញឹកញាប់ អាចរៀបចំ SSH បន្ថែមពេលក្រោយ។

## 9. ដំឡើង Visual Studio Code

Download Visual Studio Code ពី៖

```text
https://code.visualstudio.com
```

Extensions ដែលណែនាំ៖

- GitHub Pull Requests
- GitLens
- Prettier
- ESLint
- Tailwind CSS IntelliSense បើអ្នកប្រើ Tailwind CSS

ពិនិត្យ command `code`:

```bash
code --version
```

បើ macOS មិនស្គាល់ command `code`:

1. បើក VS Code។
2. ចុច `Command + Shift + P`។
3. ស្វែងរក **Shell Command: Install 'code' command in PATH**។
4. ចុច Enter។

## 10. បង្កើត Repository ដំបូង

1. បើក:

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

4. ជ្រើស **Public** ឬ **Private**។
5. Check **Add a README file**។
6. ចុច **Create repository**។

## 11. Clone Repository មកកុំព្យូទ័រ

នៅលើ GitHub repository page ចុច **Code** ហើយ copy URL។

Clone ដោយ HTTPS:

```bash
git clone https://github.com/username/hello-github.git
```

ចូលទៅ folder:

```bash
cd hello-github
```

បើកក្នុង VS Code:

```bash
code .
```

## 12. Commit ដំបូង

បង្កើត file ឈ្មោះ `notes.md` ហើយដាក់ content:

```markdown
# My GitHub Notes

Today I learned how to set up Git and GitHub.
```

ពិនិត្យ status:

```bash
git status
```

Stage file:

```bash
git add notes.md
```

Commit:

```bash
git commit -m "Add GitHub setup notes"
```

Push ទៅ GitHub:

```bash
git push
```

បើក GitHub repository page ម្តងទៀត។ អ្នកគួរឃើញ file `notes.md`។

## 13. Commands ប្រើរៀងរាល់ថ្ងៃ

ពិនិត្យ files ដែលបានកែ៖

```bash
git status
```

មើលការកែប្រែជាក់លាក់៖

```bash
git diff
```

Stage files ទាំងអស់៖

```bash
git add .
```

Commit:

```bash
git commit -m "Write a clear commit message"
```

ទាញយក code ថ្មីពី GitHub:

```bash
git pull
```

ផ្ញើ code ទៅ GitHub:

```bash
git push
```

មើល commit history:

```bash
git log --oneline
```

មើល remote URL:

```bash
git remote -v
```

## 14. Commit Message ល្អ

Commit message គួរតែខ្លី ច្បាស់ និងប្រាប់ថាអ្នកបានកែអ្វី។

ឧទាហរណ៍ល្អ៖

```text
Add homepage navigation
Fix login form validation
Update README instructions
Create student profile page
```

កុំប្រើ message មិនច្បាស់៖

```text
update
fix
changes
final
```

រូបមន្តសាមញ្ញ៖

```text
Action + what changed
```

ឧទាហរណ៍៖

- `Add contact form`
- `Fix image path`
- `Update README instructions`

## 15. `.gitignore`

`.gitignore` ប្រាប់ Git ថា file ឬ folder ណាដែលមិនគួរ commit។

ឧទាហរណ៍៖

```gitignore
node_modules/
.env
.DS_Store
dist/
build/
```

កុំ commit:

- Password
- API key
- Secret token
- Folder `node_modules`
- Build output

## 16. បញ្ហាដែលជួបញឹកញាប់

### `git` is not recognized លើ Windows

បិទ ហើយបើក PowerShell ឬ Git Bash ម្តងទៀត។ បើនៅតែមិនបាន សូមដំឡើង Git ម្តងទៀត ហើយជ្រើស option:

```text
Git from the command line and also from 3rd-party software
```

### Push rejected

ទាញយក code ថ្មីសិន៖

```bash
git pull
```

បន្ទាប់មក push ម្តងទៀត៖

```bash
git push
```

### Add file ខុស មុន commit

បើអ្នក `git add` ខុស file ប៉ុន្តែមិនទាន់ commit:

```bash
git restore --staged filename
```

ឧទាហរណ៍៖

```bash
git restore --staged notes.md
```

វាមិនលុប file ទេ។ វាគ្រាន់តែដក file នោះចេញពី commit បន្ទាប់។

## 17. Checklist

- [ ] បង្កើតគណនី GitHub
- [ ] Verify email
- [ ] បើក two-factor authentication
- [ ] ដំឡើង Git
- [ ] Configure Git name
- [ ] Configure Git email
- [ ] Configure default branch ជា `main`
- [ ] ដំឡើង VS Code
- [ ] បង្កើត repository ដំបូង
- [ ] Clone repository មកកុំព្យូទ័រ
- [ ] Commit ដំបូង
- [ ] Push ទៅ GitHub

## 18. Quick Command Reference

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main
git config --global --list
git clone repository-url
git status
git diff
git add .
git commit -m "Commit message"
git pull
git push
git log --oneline
git remote -v
```

## 19. លំហាត់អនុវត្ត

អនុវត្តតាមជំហាននេះ៖

1. បង្កើត repository ឈ្មោះ `practice-git`។
2. Clone repository មកកុំព្យូទ័រ។
3. បង្កើត file `index.html`។
4. ដាក់ heading មួយក្នុង file។
5. Run `git status`។
6. Run `git add index.html`។
7. Run `git commit -m "Add first HTML page"`។
8. Run `git push`។
9. បើក GitHub ហើយពិនិត្យថា `index.html` មាននៅលើ GitHub។

បន្ទាប់មកកែ `index.html` ម្តងទៀត ហើយអនុវត្ត `git diff`, `git add .`, `git commit`, និង `git push` ដើម្បីហ្វឹកហាត់ workflow ពេញលេញ។
