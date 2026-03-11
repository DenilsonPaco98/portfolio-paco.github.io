# 🔄 Guia Rápido: Workflow CI/CD

## O que é CI/CD?

**CI** = Continuous Integration (Integração Contínua)  
**CD** = Continuous Deployment (Deploy Contínuo)

Toda vez que você faz push, o GitHub Actions automaticamente:
1. Valida seu código
2. Testa (quando aplicável)
3. Faz deploy para produção

---

## Fluxo de Trabalho

```
You commit code
        ↓
    Push to GitHub
        ↓
    GitHub Actions triggered
        ↓
    [1] Checkout code
    [2] Setup Node.js
    [3] Install dependencies
    [4] Lint HTML
    [5] Deploy to GitHub Pages
        ↓
    ✅ Site atualizado em paco.dev
```

---

## Como Usar

### 1️⃣ Clonar Repositório

```bash
git clone https://github.com/portfolio-paco/portfolio-paco.github.io.git
cd portfolio-paco.github.io
```

### 2️⃣ Criar Branch de Feature/Dev

```bash
# Crie seu branch de desenvolvimento
git checkout -b develop

# Ou crie branches para features
git checkout -b feat/add-new-cert
git checkout -b fix/typo-in-bio
```

### 3️⃣ Fazer Mudanças

Edite `index.html` com seus dados, certificações, etc.

### 4️⃣ Testar Localmente (Opcional)

```bash
npm start
# Acesse http://localhost:8000
```

### 5️⃣ Comitar Mudanças

```bash
git add .
git commit -m "feat: add AWS Developer roadmap"
```

### 6️⃣ Push para GitHub

```bash
# Push para develop
git push origin develop
```

### 7️⃣ Criar Pull Request

No GitHub, clique em "Compare & pull request"

Descrição exemplo:
```
## Mudanças

- ✨ Adicionado AWS Developer certification ao roadmap
- 📊 Atualizado progresso de Data Analytics para 65%
- 🎨 Melhorado styling dos badges

## Type
- [ ] Bug fix
- [x] New feature
- [ ] Breaking change
```

### 8️⃣ Merge para Main

Depois que a PR passar na validação (GitHub Actions):
1. Clique "Merge pull request"
2. Confirme o merge
3. ✅ **Deploy automático acontece!**

---

## Status do Deploy

### Ver Logs do CI/CD

```
GitHub Repo → Actions → Deploy Portfolio → Runs
```

Você verá:
- ✅ Passou
- ❌ Falhou (veja o erro)
- ⏳ Executando

### Verificar Status

Toda PR terá um status:

```
✓ All checks passed
  └─ GitHub Actions (deploy workflow) - Success

Você pode fazer merge!
```

---

## Branches

### `main` (Produção)
- **URL**: paco.dev
- **Protegido**: Requer PR e validação
- **Deploy**: Automático após merge

### `develop` (Staging)
- **Para**: Desenvolvimento e testes
- **Deploy**: Não faz deploy (apenas validação)
- **Origem**: Crie features daqui

### Feature branches
- **Nome**: `feat/xyz`, `fix/xyz`
- **Origem**: `develop`
- **Destino**: `develop` ou diretamente `main`

---

## Comandos Git Rápidos

```bash
# Ver status
git status

# Ver branches
git branch -a

# Mudar de branch
git checkout develop

# Pull mudanças remotas
git pull origin develop

# Ver histórico de commits
git log --oneline

# Desfazer último commit (local)
git reset --soft HEAD~1
```

---

## Troubleshooting

### "Deploy falhou"
- Veja os logs em Actions
- Comum: Erro de sintaxe no HTML
- Solução: Corrija e faça novo push

### "Merging não permite"
- Checklist de validação falhando
- Veja "Checks" na PR
- Corrija os erros

### "Mudanças não aparecem no site"
- Espere 1-2 minutos (deploy leva tempo)
- Limpe cache do navegador (Ctrl+Shift+Del)
- Verifique se fez merge para `main`

---

## Best Practices

✅ **DO:**
- Fazer commits pequenos e frequentes
- Escrever boas mensagens de commit
- Testar localmente antes de push
- Usar branches para features
- Revisar mudanças antes de merge

❌ **DON'T:**
- Comitar diretamente em `main`
- Deixar PRs abertas indefinidamente
- Comitar arquivos grandes
- Forçar push (`git push -f`)

---

## Mensagens de Commit

Use este padrão:

```
<type>: <subject>

<body (opcional)>
```

**Types:**
- `feat`: Nova feature
- `fix`: Correção de bug
- `docs`: Documentação
- `style`: Formatação
- `refactor`: Refatoração
- `perf`: Performance
- `ci`: CI/CD changes
- `chore`: Tarefas diversas

**Exemplos:**
```
feat: add AWS Developer roadmap
fix: typo in bio section
docs: update README with workflow
ci: update deploy workflow
```

---

## Próximos Passos

1. ✅ Você já tem CI/CD configurado!
2. 🧪 Teste localmente com `npm start`
3. 🚀 Faça seu primeiro push
4. 📊 Acompanhe em GitHub Actions
5. 🎉 Veja deploy automático acontecer

---

**Dúvidas?** Confira a [documentação oficial do GitHub Actions](https://docs.github.com/en/actions)
