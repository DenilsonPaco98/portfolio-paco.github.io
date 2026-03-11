# 🔧 SOLUÇÃO: Erro de Permissão no GitHub Pages

## Problema
```
remote: Permission to DenilsonPaco98/portfolio-paco.github.io.git denied to github-actions[bot].
fatal: unable to access 'https://github.com/DenilsonPaco98/portfolio-paco.github.io.git/': 
The requested URL returned error: 403
```

## ✅ SOLUÇÃO APLICADA

Atualizei `.github/workflows/deploy.yml` com:
```yaml
- name: Deploy to GitHub Pages (main)
  if: github.ref == 'refs/heads/main' && github.event_name == 'push'
  uses: peaceiris/actions-gh-pages@v3
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: ./
    cname: paco.dev
    force_orphan: true                          # ← Novo!
    user_name: 'github-actions[bot]'            # ← Novo!
    user_email: 'github-actions[bot]@users.noreply.github.com'  # ← Novo!
```

## 🔑 PRÓXIMAS ETAPAS (IMPORTANTE!)

### 1️⃣ Verificar Configurações do Repositório

No GitHub, vá para:
**Settings → Actions → General → Workflow permissions**

☐ Selecione: **"Read and write permissions"**
☐ Ativar: **"Allow GitHub Actions to create and approve pull requests"**

### 2️⃣ Verificar Configurações de GitHub Pages

No GitHub, vá para:
**Settings → Pages → Build and deployment**

Verifique se está em:
- **Source**: `Deploy from a branch`
- **Branch**: `gh-pages` (ou selecionar `main`)

**IMPORTANTE**: Se está usando `gh-pages`, certifique-se que:
- ☐ A branch `gh-pages` existe no repositório
- ☐ Workflow permissions estão habilitadas

### 3️⃣ OPÇÃO A: Se quer usar `gh-pages` (atual)

Deixe como está agora. O workflow vai:
1. Build seu site
2. Criar/atualizar a branch `gh-pages`
3. Deploy para GitHub Pages

### 4️⃣ OPÇÃO B: Se quer usar `main` (mais simples)

Edite `.github/workflows/deploy.yml` e mude:

```yaml
- name: Deploy to GitHub Pages (main)
  uses: actions/upload-pages-artifact@v3
  with:
    path: './.'
```

Depois no GitHub Settings → Pages, selecione:
- **Source**: `GitHub Actions`

---

## 🧪 TESTE AGORA

1. Faça um commit pequeno:
```bash
git add .github/workflows/deploy.yml
git commit -m "fix: update gh-pages permissions"
git push origin main
```

2. Vá para GitHub → Actions → Deploy Portfolio
3. Veja se passa agora! ✅

---

## ❓ Se Ainda Tiver Erro

### Opção 1: Usar Deploy Key (mais seguro)

```bash
# Gere uma SSH key
ssh-keygen -t ed25519 -f gh-pages-deploy -N ""

# No GitHub:
# Settings → Deploy Keys → Add
# Cole a chave pública
```

Depois no workflow:
```yaml
- name: Deploy
  uses: peaceiris/actions-gh-pages@v3
  with:
    deploy_key: ${{ secrets.DEPLOY_KEY }}
    publish_dir: ./
```

### Opção 2: Verificar Proteção de Branch

Se `main` ou `gh-pages` estão protegidas:
- **Settings → Branches → Branch protection rules**
- Desative/atualize para permitir GitHub Actions

### Opção 3: Usar PAT (Personal Access Token)

1. GitHub → Settings → Developer settings → Personal access tokens
2. Crie um token com `repo` + `workflow`
3. No repositório → Settings → Secrets → New
   - Nome: `GH_TOKEN`
   - Valor: seu token
4. No workflow, use `${{ secrets.GH_TOKEN }}`

---

## 🎯 PRÓXIMO PASSO

1. ✅ Atualizei o workflow (feito!)
2. Verifique as permissões no GitHub (próximo)
3. Faça novo push para testar

---

## 📋 CHECKLIST

- [ ] Atualizei `.github/workflows/deploy.yml`
- [ ] Verifiquei "Workflow permissions" = Read and write
- [ ] Verifiquei GitHub Pages settings
- [ ] Fiz novo push para testar
- [ ] ✅ Deploy funcionando!

---

Aviso-me quando quiser testar! 🚀
