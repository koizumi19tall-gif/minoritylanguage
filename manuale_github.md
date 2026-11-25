# **Manuale Completo di GitHub**
# *Dalle Basi alle Funzionalità Avanzate*

---

**Autore:** Vibe Code (Mistral AI)  
**Versione:** 1.0  
**Data:** 2024  
**Lingua:** Italiano  

---

## 📖 **SOMMARIO**

### PARTE 1: INTRODUZIONE
- [1. Cos'è Git e GitHub](#1-cosè-git-e-github)
- [2. Differenze tra Git e GitHub](#2-differenze-tra-git-e-github)
- [3. Terminologia di base](#3-terminologia-di-base)

### PARTE 2: CONFIGURAZIONE
- [4. Creare account GitHub](#4-creare-account-github)
- [5. Installare Git](#5-installare-git)
- [6. Configurare Git](#6-configurare-git)
- [7. Autenticazione (HTTPS/SSH/CLI)](#7-autenticazione)

### PARTE 3: REPOSITORY
- [8. Creare repository](#8-creare-repository)
- [9. Clonare repository](#9-clonare-repository)
- [10. Fork e sincronizzazione](#10-fork-e-sincronizzazione)

### PARTE 4: COMANDI GIT FONDAMENTALI
- [11. git add, commit, status, diff](#11-comandi-base)
- [12. git log e storia](#12-git-log)
- [13. Working Directory vs Staging Area](#13-aree-di-lavoro)

### PARTE 5: BRANCH E MERGE
- [14. Creare e gestire branch](#14-branch)
- [15. Merge e conflitti](#15-merge)
- [16. Rebase](#16-rebase)
- [17. git push, pull, fetch](#17-sincronizzazione-remota)

### PARTE 6: COLLABORAZIONE
- [18. Pull Request](#18-pull-request)
- [19. Issue e Bug Tracking](#19-issue)
- [20. Code Review](#20-code-review)
- [21. GitHub Projects e Wiki](#21-progetti-e-wiki)

### PARTE 7: GITHUB AVANZATO
- [22. GitHub Actions (CI/CD)](#22-github-actions)
- [23. GitHub Pages](#23-github-pages)
- [24. GitHub CLI](#24-github-cli)
- [25. GitHub API](#25-github-api)
- [26. Webhook](#26-webhook)
- [27. Codespaces](#27-codespaces)
- [28. Copilot](#28-copilot)

### PARTE 8: GIT AVANZATO
- [29. Reset, Revert, Restore](#29-reset-revert)
- [30. Stash](#30-stash)
- [31. Tag](#31-tag)
- [32. Submoduli](#32-submoduli)
- [33. Git LFS](#33-git-lfs)

### PARTE 9: BEST PRACTICES
- [34. Conventional Commits](#34-conventional-commits)
- [35. Git Flow vs GitHub Flow](#35-workflow)
- [36. Sicurezza](#36-sicurezza)

### PARTE 10: RISOLUZIONE PROBLEMI
- [37. Errori comuni](#37-errori-comuni)
- [38. Recupero dati](#38-recupero-dati)

### PARTE 11: STRUMENTI
- [39. Client GUI](#39-client-gui)
- [40. Integrazioni IDE](#40-integrazioni-ide)

### PARTE 12: GLOSSARIO
- [41. Termini chiave](#41-glossario)

### PARTE 13: RISORSE
- [42. Documentazione ufficiale](#42-risorse)

---

## 🔍 **TERMINI CHIAVE PER LA RICERCA**

Usa **Ctrl+F** per cercare: `git`, `github`, `repository`, `commit`, `branch`, `merge`, `pull request`, `push`, `pull`, `clone`, `fork`, `issue`, `actions`, `pages`, `ssh`, `https`, `cli`, `workflow`, `conflict`, `rebase`, `stash`, `tag`, `lfs`, `webhook`, `api`, `copilot`, `codespaces`, `reset`, `revert`, `reset hard`, `reset soft`

---

# **PARTE 1: INTRODUZIONE**

---

## **1. Cos'è Git e GitHub**

### Git
**Git** è un **sistema di controllo versione distribuito** (DVCS) creato da Linus Torvalds nel 2005.
- **Distribuito**: Ogni sviluppatore ha una copia completa della storia
- **Velocità**: Operazioni locali estremamente veloci
- **Branch economici**: Creare branch è veloce e leggero
- **Integrità**: Usa hash SHA-1 per garantire l'integrità dei dati

### GitHub
**GitHub** è una **piattaforma web** basata su Git che offre:
- Hosting di repository Git
- Strumenti di collaborazione (Pull Request, Issue, Code Review)
- Funzionalità aggiuntive (Actions, Pages, Wiki)
- Community di sviluppatori

**GitHub è stato acquisito da Microsoft nel 2018** ma rimane indipendente e open source.

---

## **2. Differenze tra Git e GitHub**

| Git | GitHub |
|-----|--------|
| Sistema di controllo versione | Piattaforma di hosting |
| Software open source | Servizio web (freemium) |
| Funziona offline | Richiede connessione internet |
| Comandi da terminale | Interfaccia web + CLI |
| Locale | Remoto |

**Analogia**: Git è il motore, GitHub è il parcheggio con servizi.

---

## **3. Terminologia di Base**

| Termine | Descrizione | Esempio |
|---------|-------------|---------|
| **Repository** | Cartella con progetto e storia | `my-project` |
| **Commit** | Snapshot delle modifiche | `git commit -m "Fix bug"` |
| **Branch** | Linea di sviluppo parallela | `main`, `dev`, `feature/login` |
| **Merge** | Unione di due branch | `git merge feature` |
| **Pull Request** | Richiesta di merge su GitHub | PR #123 |
| **Push** | Invio modifiche al remoto | `git push origin main  # Inviare le modifiche al tuo fork` |
| **Pull** | Scaricamento modifiche | `git pull origin main` |
| **Clone** | Copia locale di repository | `git clone url` |
| **Fork** | Copia di repository altrui | Fork di `user/repo` |
| **Issue** | Segnalazione bug/feature | Issue #456 |

---

# **PARTE 2: CONFIGURAZIONE**

---

## **4. Creare un Account GitHub**

1. Visitare [github.com](https://github.com)
2. Cliccare su "Sign up"
3. Inserire username, email e password
4. Scegliere il piano (Free/Pro/Team/Enterprise)
5. Completare il quiz di benvenuto
6. Verificare l'email

**Piani:**
- **Free**: Gratis per repo pubblici e privati (con limiti)
- **Pro**: $4/mese per sviluppatori
- **Team**: $4/utente/mese
- **Enterprise**: Soluzioni aziendali

---

## **5. Installare Git**

### Windows
- **Metodo 1**: Scaricare da [git-scm.com](https://git-scm.com/download/win)
- **Metodo 2**: `choco install git` (Chocolatey)
- **Metodo 3**: `scoop install git` (Scoop)

### macOS
- **Metodo 1**: `brew install git` (Homebrew)
- **Metodo 2**: `xcode-select --install` (XCode Tools)

### Linux
- Debian/Ubuntu: `sudo apt install git`
- Fedora: `sudo dnf install git`
- Arch: `sudo pacman -S git`

**Verifica**: `git --version`

---

## **6. Configurare Git Localmente**

```bash
# Configurazione globale
git config --global user.name "Il Tuo Nome"
git config --global user.email "tua@email.com"
git config --global core.editor "code --wait"  # VS Code
git config --global color.ui true

# Configurazione line endings
git config --global core.autocrlf input   # Linux/macOS
git config --global core.autocrlf true    # Windows

# Verificare configurazione
git config --list
```

---

## **7. Autenticazione**

### HTTPS
1. Generare **Personal Access Token** (PAT) su GitHub → Settings → Developer settings
2. Usare token come password:
```bash
git clone https://github.com/username/repo.git
# Username: tuo username
# Password: Personal Access Token
```
3. Salvare credenziali:
```bash
git config --global credential.helper cache      # 15 min
git config --global credential.helper wincred   # Windows
git config --global credential.helper store     # macOS/Linux
```

### SSH
1. Generare chiave:
```bash
ssh-keygen -t ed25519 -C "tua@email.com"
```
2. Aggiungere chiave a ssh-agent:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```
3. Aggiungere chiave pubblica a GitHub (Settings → SSH and GPG keys)
4. Testare: `ssh -T git@github.com`
5. Clonare: `git clone git@github.com:username/repo.git`

### GitHub CLI
```bash
# Installare
brew install gh          # macOS
choco install gh        # Windows
sudo apt install gh     # Linux

# Autenticarsi
gh auth login
```

---

# **PARTE 3: REPOSITORY**

---

## **8. Creare un Repository**

### Da Web
1. GitHub → **+** → New repository
2. Inserire nome, descrizione
3. Scegliere la visibilità (Public/Private)
4. Inizializzare con un file README, .gitignore, License (opzionale)
5. Cliccare "Create repository"

### Da Terminale
```bash
# Creare cartella e repository
mkdir my-project
cd my-project
git init

# Aggiungere file
echo "# My Project" > README.md
git add README.md
git commit -m "Initial commit"

# Creare su GitHub e push
gh repo create my-project --public --source=. --push
```

---

## **9. Clonare un Repository**

```bash
# Via HTTPS
git clone https://github.com/username/repo.git

# Via SSH
git clone git@github.com:username/repo.git

# In cartella specifica
git clone https://github.com/username/repo.git my-folder

# Branch specifico
git clone --branch branch-name https://github.com/username/repo.git

# Profondità limitata
git clone --depth 1 https://github.com/username/repo.git
```

---

## **10. Fork e Sincronizzazione**

### Fork
1. Da interfaccia web: Repository → Fork (in alto a destra)
2. Scegliere account di destinazione

### Sincronizzare Fork
```bash
# Clonare il fork
git clone git@github.com:tuo-username/repo.git
cd repo

# Aggiungere upstream (repository originale)
git remote add upstream https://github.com/utente-originale/repo.git

# Sincronizzare
git fetch upstream  # Scarica le modifiche dall'upstream
git checkout main  # Switchare sul branch main
git merge upstream/main  # Unire le modifiche dell'upstream
git push origin main  # Inviare le modifiche al tuo fork
```

---

# **PARTE 4: COMANDI GIT FONDAMENTALI**

---

## **11. Comandi Base**

### git add
```bash
git add file.txt           # File specifico
git add .                  # Tutti i file
git add *.js              # Pattern
git add folder/            # Cartella
git add -A                # Tutti (inclusi eliminati)
git add -u                # Solo modificati/eliminati
```

### git commit
```bash
git commit -m "Messaggio"                          # Commit con messaggio
git commit -a -m "Commit all tracked files"         # Aggiunge e commita
git commit --amend -m "New message"                # Modifica ultimo commit
git commit --allow-empty -m "Trigger build"       # Commit vuoto
```

### git status
```bash
git status          # Stato completo
git status -s       # Formato compatto
```

### git diff
```bash
git diff             # Differenze nel Working Directory
git diff file.txt    # Differenze in file specifico
git diff --staged   # Differenze in Staging Area
git diff commit1..commit2  # Differenze tra commit
```

---

## **12. git log e Storia**

```bash
git log                     # Log base
git log --oneline           # Compatto (1 riga per commit)
git log --graph --oneline --decorate  # Con grafico
git log -p                   # Con patch (differenze)
git log --stat               # Con statistiche
git log -n 5                # Ultimi 5 commit
git log --since="2024-01-01"  # Da data specifica
git log --author="username" # Di autore specifico
git log --grep="fix"        # Cerca nel messaggio
git log file.txt            # Storia di un file

# Alias utile
git config --global alias.lg "log --graph --oneline --decorate --all"
```

---

## **13. Working Directory vs Staging Area**

```
Working Directory (File modificati non aggiunti)
       ↓
Staging Area (Index) - File pronti per commit
       ↓
Local Repository - Commit salvati localmente
       ↓
Remote Repository - Commit su GitHub
```

**Workflow tipico:**
1. Modificare file nel Working Directory
2. `git add` (Staging Area)
3. `git commit` (Local Repository)
4. `git push` (Remote Repository)

---

# **PARTE 5: BRANCH E MERGE**

---

## **14. Creare e gestire branch**

### git branch
```bash
git branch                    # Elenca branch locali
git branch -a                 # Elenca tutti i branch
git branch -r                 # Elenca branch remoti
git branch feature/login      # Crea nuovo branch
git branch -d feature/login   # Elimina branch locale
git branch -D feature/login   # Elimina branch locale (forzato)
git branch -m old new         # Rinomina branch
```

### git checkout / git switch
```bash
# Switchare su branch esistente
git checkout main  # Switchare sul branch main
git switch main

# Creare e switchare su nuovo branch
git checkout -b feature/login
git switch -c feature/login

# Ripristinare file
git checkout -- file.txt
git restore file.txt
```

---

## **15. Merge e Conflitti**

### git merge
```bash
# Switchare su branch di destinazione
git checkout main  # Switchare sul branch main

# Merge di un branch nel branch corrente
git merge feature/login  # Unisce feature/login nel branch corrente

# Merge senza fast-forward
git merge --no-ff  # Crea sempre un commit di merge feature/login

# Merge squash (unisce tutti i commit in uno)
git merge --squash  # Unisce tutti i commit in uno solo feature/login
```

### Risolvere Conflitti
1. Git segnalerà i file con conflitto
2. Aprire i file con conflitto e risolvere manualmente:
```
<<<<<<< HEAD
Contenuto del branch corrente
=======
Contenuto del branch che stai mergiando
>>>>>>> feature/login
```
3. Aggiungere file risolti: `git add file.txt`
4. Completare merge: `git commit`

**Strumenti:**
- VS Code: Interfaccia grafica integrata
- `git mergetool`: Tool esterni (meld, kdiff3)
- `git diff`: Visualizzare differenze

---

## **16. Rebase**

**Rebase** riscrive la storia dei commit per mantenere una linea lineare.

```bash
# Switchare sul branch da rebasare
git checkout feature/login

# Rebase sul branch di destinazione
git rebase main  # Rebase sul branch main

# Rebase interattivo (ultimi 3 commit)
git rebase -i HEAD~3

# Dopo conflict
git rebase --continue   # Continua
git rebase --abort     # Annulla
git rebase --skip      # Salta commit
```

**Differenza merge vs rebase:**
- **Merge**: Crea commit di merge, mantiene storia
- **Rebase**: Riscrive storia, linea lineare

**Quando usare rebase:**
- ✅ Branch locali non condivisi
- ✅ Prima di fare Pull Request
- ❌ Branch condivisi con altri

---

## **17. Sincronizzazione Remota**

### git push
```bash
git push                     # Push su branch corrente
git push origin main  # Inviare le modifiche al tuo fork         # Push su branch specifico
git push -u origin main      # Imposta upstream
git push --force             # Force push (ATTENZIONE!)
git push --force-with-lease  # Force push sicuro
git push --all               # Push tutti i branch
git push --tags              # Push tutti i tag
```

### git pull
```bash
git pull                      # Pull su branch corrente
git pull origin main          # Pull da branch specifico
git pull --rebase             # Pull con rebase (evita merge commit)
```

### git fetch
```bash
git fetch                     # Scarica modifiche remote
git fetch origin              # Da remote specifico
git fetch --prune             # Rimuove riferimenti a branch eliminati
```

**Differenza:**
- `git fetch`: Scarica solo modifiche
- `git pull`: Scarica e fa merge

---

# **PARTE 6: COLLABORAZIONE**

---

## **18. Pull Request (PR)**

### Creare PR da Web
1. Push branch su GitHub: `git push -u origin feature/login`
2. GitHub → Repository → Pull Requests → New Pull Request
3. Selezionare:
   - **Base branch**: Branch di destinazione (es: `main`)
   - **Compare branch**: Branch sorgente (es: `feature/login`)
4. Compilare:
   - Titolo
   - Descrizione
   - Reviewers
   - Labels
   - Projects
   - Milestone
5. Cliccare "Create Pull Request"

### Creare PR da CLI
```bash
gh pr create --base main --head feature/login --title "Titolo" --body "Descrizione"
```

### Metodi di Merge
1. **Create a merge commit**: Crea commit di merge (default)
2. **Squash and merge**: Unisce tutti i commit in uno
3. **Rebase and merge**: Riscrive storia e fa merge

---

## **19. Issue e Bug Tracking**

### Creare Issue
1. GitHub → Repository → Issues → New Issue
2. Compilare:
   - Titolo
   - Descrizione
   - Assignees
   - Labels
   - Projects
   - Milestone
3. Cliccare "Submit new issue"

### Template Issue
```markdown
### Descrizione del bug
**Passaggi per riprodurre:**
1. Vai a...
2. Clicca su...

**Comportamento atteso:**
...

**Comportamento effettivo:**
...

**Ambiente:**
- OS: [e.g. Windows 10]
- Browser: [e.g. Chrome 120]
```

### Collegare Issue a PR
- **Manualmente**: Da interfaccia web
- **Automaticamente**: Usare keyword nei commit:
  - `Fix #123` o `Fixes #123`
  - `Close #123` o `Closes #123`
  - `Resolve #123` o `Resolves #123`

---

## **20. Code Review**

### Best Practices
**Per chi scrive:**
- PR piccoli (< 400 righe)
- Descrizione chiara
- Test inclusi
- Documentazione aggiornata

**Per chi reviewa:**
- Sii tempestivo
- Sii costruttivo
- Sii specifico
- Chiedi chiarimenti
- Approva solo se: codice funziona, test passano, documentazione OK

---

## **21. GitHub Projects e Wiki**

### Projects (Kanban)
1. Repository → Projects → New Project
2. Scegliere template (Board, Roadmap, Iterations)
3. Configurare colonne
4. Aggiungere Issue e PR

### Wiki
1. Abilitare Wiki: Repository Settings → Features → Wiki
2. Aggiungere pagine: New Page
3. Scrivere in Markdown
4. Collegare pagine: `[[Pagina Principale]]`

---

# **PARTE 7: GITHUB AVANZATO**

---

## **22. GitHub Actions (CI/CD)**

### Cos'è
GitHub Actions è una piattaforma di **automazione CI/CD** integrata in GitHub.

**Componenti:**
- **Workflow**: File YAML (`.github/workflows/nome.yml`)
- **Eventi**: Trigger (push, pull_request, schedule, ecc.)
- **Job**: Insieme di passaggi
- **Step**: Singola azione
- **Actions**: Script riutilizzabili
- **Runners**: Macchine che eseguono workflow

### Esempio Workflow
```yaml
name: CI Build

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'
      - run: npm install
      - run: npm test
      - run: npm run build
```

### Eventi Comuni
```yaml
on:
  push:              # Push su branch
    branches: [ main ]
  pull_request:      # Pull Request
    branches: [ main ]
  schedule:          # Cron
    - cron: '0 0 * * *'  # Ogni giorno a mezzanotte
  workflow_dispatch: # Manuale
```

### Esempio Deploy GitHub Pages
```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'
      - run: npm install
      - run: npm run build
      - uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

---

## **23. GitHub Pages**

### Creare Sito Statico
**Metodo 1: Da branch main**
1. Creare repository `username.github.io` (sito personale) o qualsiasi nome (progetto)
2. Abilitare Pages: Repository Settings → Pages → Branch: main → /root
3. Aggiungere `index.html`
4. Push: `git push origin main  # Inviare le modifiche al tuo fork`
5. Visitare: `https://username.github.io` o `https://username.github.io/repo`

**Metodo 2: Da branch gh-pages**
```bash
git checkout --orphan gh-pages
git commit --allow-empty -m "Initial commit"
git push origin gh-pages
```

**Metodo 3: Da cartella /docs**
1. Creare cartella `/docs`
2. Aggiungere file HTML in `/docs`
3. Abilitare Pages da `/docs`

### Jekyll
```bash
# Installare
gem install jekyll bundler

# Creare nuovo sito
jekyll new my-site
cd my-site

# Eseguire localmente
bundle exec jekyll serve
```

---

## **24. GitHub CLI**

### Installazione
```bash
brew install gh          # macOS
choco install gh        # Windows
sudo apt install gh     # Linux
```

### Comandi Principali
```bash
# Autenticazione
gh auth login
gh auth status

# Repository
gh repo clone username/repo
gh repo create nome --public --clone
gh repo view

# Pull Request
gh pr list
gh pr view 123
gh pr create --base main --head feature --title "Titolo"
gh pr checkout 123
gh pr merge 123

# Issue
gh issue list
gh issue view 123
gh issue create --title "Titolo" --body "Descrizione"

# Workflow
gh workflow list
gh workflow run nome.yml
```

---

## **25. GitHub API**

### REST API
**Base URL:** `https://api.github.com`

**Autenticazione:**
```bash
curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/user
```

**Esempi:**
```bash
# Ottenere info utente
curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/user

# Ottenere repository
curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/users/username/repos

# Creare repository
curl -X POST -H "Authorization: token YOUR_TOKEN" \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/user/repos \
  -d '{"name":"new-repo","private":false}'
```

### GraphQL API
**Base URL:** `https://api.github.com/graphql`

**Esempio:**
```graphql
query {
  user(login: "username") {
    name
    bio
    repositories(first: 5) {
      nodes {
        name
        stargazers {
          totalCount
        }
      }
    }
  }
}
```

**Eseguire:**
```bash
curl -X POST -H "Authorization: bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  https://api.github.com/graphql \
  -d '{"query": "query { user(login: \"username\") { name } }"}'
```

---

## **26. Webhook**

### Configurare Webhook
1. Repository Settings → Webhooks → Add webhook
2. Configurare:
   - **Payload URL**: URL del server
   - **Content type**: `application/json`
   - **Secret**: (Opzionale)
   - **Events**: push, pull_request, issues, ecc.

### Eventi Comuni
| Evento | Descrizione | Payload |
|--------|-------------|---------|
| `push` | Push su branch | Commit, branch |
| `pull_request` | PR aperta/chiusa | PR, repository |
| `issues` | Issue aperta/chiusa | Issue, repository |

### Handler Node.js
```javascript
const express = require('express');
const crypto = require('crypto');
const app = express();

const SECRET = 'your-secret';

app.use(express.json());

app.post('/webhook', (req, res) => {
  const signature = req.headers['x-hub-signature-256'];
  const hmac = crypto.createHmac('sha256', SECRET);
  const digest = 'sha256=' + hmac.update(JSON.stringify(req.body)).digest('hex');
  
  if (signature !== digest) {
    return res.status(401).send('Invalid signature');
  }
  
  const event = req.headers['x-github-event'];
  const payload = req.body;
  
  switch (event) {
    case 'push':
      console.log('Push ricevuto:', payload.ref);
      break;
    case 'pull_request':
      console.log('PR ricevuta:', payload.pull_request.title);
      break;
  }
  
  res.status(200).send('OK');
});

app.listen(3000);
```

---

## **27. GitHub Codespaces**

### Cos'è
Ambiente di sviluppo **cloud-based** con VS Code nel browser.

**Caratteristiche:**
- Contenitori Docker preconfigurati
- Accesso da qualsiasi dispositivo
- Integrazione con GitHub

**Piani:**
- Free: 60 ore/mese (2-core, 4GB RAM)
- Pro: $0.18-$1.44/ora

### Creare Codespace
```bash
# Da CLI
gh codespace create --repo username/repo --branch main
```

### Configurare devcontainer.json
```json
{
  "name": "My Project",
  "dockerFile": "Dockerfile",
  "forwardPorts": [3000, 8080],
  "postCreateCommand": "npm install",
  "extensions": ["dbaeumer.vscode-eslint"]
}
```

---

## **28. GitHub Copilot**

### Cos'è
**AI pair programmer** sviluppato da GitHub e OpenAI.

**Caratteristiche:**
- Completamento codice in tempo reale
- Spiegazione codice
- Generazione funzioni complete
- Debugging
- Multi-linguaggio

**Piani:**
- Free: 30 giorni di prova
- Pro: $10/mese
- Business: $19/utente/mese

### Installazione
- **VS Code**: Extensions → GitHub Copilot
- **JetBrains**: Settings → Plugins → GitHub Copilot

### Uso
- Iniziare a scrivere → Copilot suggerisce
- Premere **Tab** per accettare
- Scrivere commento → Copilot genera codice
- Selezionare codice → **Ctrl+I** per spiegazione

---

# **PARTE 8: GIT AVANZATO**

---

## **29. Reset, Revert, Restore**

### git reset
```bash
git reset --soft abc1234   # Sposta HEAD, mantiene staging e working
git reset abc1234           # Mixed (default): sposta HEAD e staging
git reset --hard abc1234   # Sposta HEAD, staging e working (ATTENZIONE!)
git reset HEAD file.txt     # Toglie file da staging
```

### git revert
```bash
git revert abc1234            # Crea commit che annulla modifiche
git revert --no-commit abc1234  # Senza commit automatico
git revert abc1234..def5678    # Range di commit
```

**Differenza:**
- **Reset**: Modifica storia (pericoloso se pushato)
- **Revert**: Crea nuovo commit (sicuro)

### git restore
```bash
git restore file.txt          # Ripristina da working directory
git restore --staged file.txt # Ripristina da staging
git restore --source abc1234 file.txt  # Ripristina da commit
```

---

## **30. Stash**

```bash
git stash                     # Salva modifiche
git stash save "Messaggio"    # Con messaggio
git stash -u                  # Incluse file untracked
git stash list                # Elenca stash
git stash apply               # Applica ultimo stash
git stash apply stash@{1}    # Applica stash specifico
git stash pop                 # Applica e rimuove
git stash drop stash@{1}     # Rimuove stash
git stash clear               # Rimuove tutti gli stash
git stash branch new-branch  # Crea branch da stash
```

---

## **31. Tag**

### Creare Tag
```bash
git tag v1.0.0                     # Tag leggero
git tag -a v1.0.0 -m "Versione 1.0.0"  # Tag annotato
git tag -s v1.0.0 -m "Versione 1.0.0"  # Tag firmato
git tag v1.0.0 abc1234               # Tag su commit specifico
```

### Gestire Tag
```bash
git tag                          # Elenca tag
git tag -l "v1.*"                # Filtra tag
git show v1.0.0                   # Visualizza tag
git push origin v1.0.0           # Push tag
git push origin --tags           # Push tutti i tag
git tag -d v1.0.0                 # Elimina tag locale
git push origin :refs/tags/v1.0.0 # Elimina tag remoto
```

---

## **32. Submoduli**

```bash
# Aggiungere submodulo
git submodule add https://github.com/username/library.git libs/library

# Clonare con submoduli
git clone --recurse-submodules https://github.com/username/repo.git

# Inizializzare submoduli (dopo clone)
git submodule init
git submodule update

# Aggiornare submodulo
git submodule update --remote libs/library

# Rimuovere submodulo
git submodule deinit libs/library
git rm libs/library
rm -rf .git/modules/libs/library
```

**File `.gitmodules`:**
```ini
[submodule "libs/library"]
    path = libs/library
    url = https://github.com/username/library.git
```

---

## **33. Git LFS (Large File Storage)**

### Installazione
```bash
# Windows/macOS/Linux
git lfs install
```

### Uso
```bash
# Track file
git lfs track "*.psd"
git lfs track "*.zip"

# Verificare
git lfs ls-files

# Aggiungere e committare
git add .gitattributes
git add file.psd
git commit -m "Add PSD with LFS"
git push origin main  # Inviare le modifiche al tuo fork
```

**File `.gitattributes`:**
```
*.psd filter=lfs diff=lfs merge=lfs -text
*.zip filter=lfs diff=lfs merge=lfs -text
```

---

# **PARTE 9: BEST PRACTICES**

---

## **34. Conventional Commits**

**Formato:** `tipo(ambito): descrizione`

**Tipi:**
- `feat`: Nuova funzionalità
- `fix`: Correzione bug
- `docs`: Documentazione
- `style`: Formattazione
- `refactor`: Refactoring
- `perf`: Prestazioni
- `test`: Test
- `build`: Build
- `ci`: CI/CD
- `chore`: Manutenzione

**Esempi:**
```
feat(login): add OAuth authentication
fix(api): handle null values in response
docs(readme): update installation instructions
refactor(user-service): extract validation logic
```

---

## **35. Git Flow vs GitHub Flow**

### Git Flow
**Branch:**
- `main`: Produzione
- `develop`: Sviluppo
- `feature/*`: Nuove funzionalità
- `release/*`: Preparazione release
- `hotfix/*`: Correzioni urgenti

### GitHub Flow
**Principi:**
1. Branch `main` sempre deployabile
2. Feature branch per ogni modifica
3. Pull Request per merge in `main`
4. Code review obbligatoria
5. Deploy dopo merge

### Trunk-Based Development
- Tutti lavorano su `main`
- Branch brevi (ore/giorni)
- Feature flag per funzionalità incomplete
- CI/CD integrato

---

## **36. Sicurezza**

### Secret Scanning
- Scansiona repository per segreti (token, password, ecc.)
- Avvisa se trovati
- **Attivare:** Repository Settings → Security & Analysis → Secret scanning

### Dependency Review
- Analizza dipendenze per vulnerabilità
- **Attivare:** Repository Settings → Security & Analysis → Dependency graph

### CodeQL
- Analisi statica del codice
- **Attivare:** Repository Settings → Security & Analysis → Code scanning

---

# **PARTE 10: RISOLUZIONE PROBLEMI**

---

## **37. Errori Comuni**

| Errore | Causa | Soluzione |
|--------|-------|----------|
| `fatal: not a git repository` | Non in repo Git | `git init` o `cd` cartella |
| `fatal: 'origin' does not appear...` | Remote non configurato | `git remote add origin url` |
| `error: failed to push some refs` | Branch remoto non aggiornato | `git pull --rebase` poi `git push` |
| `error: local changes would be overwritten` | Modifiche locali non committate | `git stash` o `git commit` |
| `error: Permission denied (publickey)` | Chiave SSH non configurata | Configurare chiave SSH |
| `error: pathspec 'branch' did not match` | Branch non esiste | Verificare con `git branch -a` |

---

## **38. Recupero Dati**

### Recuperare File Eliminati
```bash
# Da commit precedente
git log -- file.txt
git checkout abc1234 -- file.txt

# Da working directory
git restore file.txt

# Da stash
git stash apply
```

### Recuperare Commit Persi
```bash
# Usare reflog
git reflog

# Trovare commit (es: abc1234)
git checkout abc1234
git branch recovered-branch abc1234

# Usare fsck
git fsck --lost-found
git show dangling-commit
git branch recovered-branch dangling-commit
```

### Risolvere Conflitti
1. `git status` per vedere file con conflict
2. Aprire file e risolvere:
```
<<<<<<< HEAD
Contenuto corrente
=======
Contenuto in merge
>>>>>>> feature
```
3. `git add file.txt`
4. `git commit`

---

# **PARTE 11: STRUMENTI**

---

## **39. Client GUI**

| Client | Piattaforma | Sito |
|--------|-------------|------|
| GitHub Desktop | Windows, macOS | [desktop.github.com](https://desktop.github.com) |
| GitKraken | Windows, macOS, Linux | [gitkraken.com](https://www.gitkraken.com) |
| Sourcetree | Windows, macOS | [sourcetreeapp.com](https://www.sourcetreeapp.com) |
| Fork | macOS, Windows | [git-fork.com](https://git-fork.com) |

---

## **40. Integrazioni IDE**

| IDE | Supporto Git |
|-----|--------------|
| VS Code | Integrato + estensioni (GitLens) |
| IntelliJ | Integrato |
| PyCharm | Integrato |
| Eclipse | Plugin EGit |
| NetBeans | Integrato |

---

# **PARTE 12: GLOSSARIO**

---

## **41. Glossario**

| Termine | Definizione |
|---------|-------------|
| **Add** | Aggiunge file all'area di staging |
| **Branch** | Linea di sviluppo parallela |
| **Checksum** | Hash SHA-1 che identifica un commit |
| **Clone** | Copia di un repository remoto |
| **Commit** | Snapshot delle modifiche |
| **Conflict** | Situazione in cui Git non può unire branch |
| **Diff** | Differenze tra file/commit |
| **Fetch** | Scarica modifiche remote senza merge |
| **Fork** | Copia di repository altrui |
| **HEAD** | Puntatore al commit corrente |
| **Index** | Area di staging |
| **Merge** | Unione di due branch |
| **Origin** | Nome predefinito del remote |
| **Pull** | Fetch + merge |
| **Push** | Invio commit al remote |
| **Rebase** | Riscrittura della storia |
| **Ref** | Riferimento a commit (branch, tag, HEAD) |
| **Remote** | Repository su server |
| **Reset** | Sposta HEAD e opzionalmente modifica staging/working |
| **Revert** | Crea commit che annulla modifiche |
| **Stash** | Salva modifiche temporaneamente |
| **Tag** | Puntatore statico a commit |
| **Upstream** | Repository originale da cui si è forkato |
| **Working Directory** | Cartella dove si lavorano i file |
| **Issue** | Segnalazione bug/feature |
| **Pull Request** | Richiesta di merge |
| **Workflow** | Processo automatizzato |
| **Runner** | Macchina che esegue workflow |
| **Action** | Script riutilizzabile |
| **Job** | Insieme di passaggi |
| **Step** | Singola azione/comando |
| **Event** | Trigger per workflow |
| **Webhook** | Notifica HTTP |
| **Secret** | Variabile segreta |

---

# **PARTE 13: RISORSE**

---

## **42. Documentazione e Risorse**

### Git
- [Git Documentation](https://git-scm.com/doc)
- [Pro Git (Libro gratuito)](https://git-scm.com/book/it/v2)
- [Git Reference](https://git-scm.com/docs)

### GitHub
- [GitHub Docs](https://docs.github.com/it)
- [GitHub Guides](https://guides.github.com/)
- [GitHub Skills](https://skills.github.com/)
- [GitHub Blog](https://github.blog/)

### Community
- [GitHub Community Forum](https://github.community/)
- [Stack Overflow (git)](https://stackoverflow.com/questions/tagged/git)
- [Stack Overflow (github)](https://stackoverflow.com/questions/tagged/github)
- [r/git (Reddit)](https://www.reddit.com/r/git/)

### Corsi
- [GitHub Learning Lab](https://lab.github.com/)
- [FreeCodeCamp Git Course](https://www.youtube.com/watch?v=RGOj5yH7evk)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)

### Certificazioni
- [GitHub Certified Developer](https://github.com/certification)

---

## **🎓 Conclusione**

Questo manuale copre **tutti gli aspetti di GitHub**, dalle basi alle funzionalità avanzate.

**Prossimi passi:**
1. **Pratica** con progetti personali
2. **Contribuisci** a progetti open source
3. **Esplora** nuove funzionalità
4. **Aggiornati** con la documentazione ufficiale

**Ricorda:**
- **Git** è lo strumento, **GitHub** è la piattaforma
- **Commit spesso**, **push spesso**
- **Collabora** con altri sviluppatori
- **Impara dagli errori**

**Buon coding!** 🚀

---

**Autore:** Vibe Code (Mistral AI)  
**Versione:** 1.0  
**Data:** 2024  
**Licenza:** CC BY-SA 4.0

---

*Per aggiornamenti: [GitHub Docs](https://docs.github.com/it)*
