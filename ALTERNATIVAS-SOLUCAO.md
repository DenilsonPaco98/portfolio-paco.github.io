# 🔧 ALTERNATIVAS DE SOLUÇÃO - Erro 403 GitHub Actions

Se a solução anterior não funcionar, tente estas opções:

---

## OPÇÃO 1: Mudar para Deploy via Actions (RECOMENDADO) ⭐

Mais simples e não precisa de branch `gh-pages`.

### Passo 1: Edite `.github/workflows/deploy.yml`

Substitua a seção Deploy por:

```yaml
      - name: Upload Pages artifact
        if: github.ref == 'refs/heads/main' && github.event_name == 'push'
        uses: actions/upload-pages-artifact@v3
        with:
          path: './.'

      - name: Deploy to GitHub Pages
        if: github.ref == 'refs/heads/main' && github.event_name == 'push'
        id: deployment
        uses: actions/deploy-pages@v2
```

### Passo 2: Configure no GitHub

Settings → Pages:
- Source: **GitHub Actions** (em vez de branch)

### Passo 3: Teste

```bash
git add .github/workflows/deploy.yml
git commit -m "fix: use github actions deploy"
git push origin main
```

**Vantagens:**
- ✅ Mais simples
- ✅ Não precisa de branch gh-pages
- ✅ Menos permissões necessárias

---

## OPÇÃO 2: Usar Deploy Key (MAIS SEGURO)

Crie uma SSH key dedicada para o deploy.

### Passo 1: Gerar SSH Key (local)

```bash
ssh-keygen -t ed25519 -f gh-pages-deploy -N ""

# Cria 2 arquivos:
# - gh-pages-deploy (privada)
# - gh-pages-deploy.pub (pública)
```

### Passo 2: Adicionar Chave Pública no GitHub

Settings → Deploy keys:
1. Clique "Add deploy key"
2. Título: "GitHub Actions Deploy"
3. Cole conteúdo de `gh-pages-deploy.pub`
4. ☑ Allow write access
5. Add key

### Passo 3: Adicionar Chave Privada nos Secrets

Settings → Secrets and variables → Actions:
1. New repository secret
2. Nome: `DEPLOY_KEY`
3. Valor: Conteúdo de `gh-pages-deploy` (privada)
4. Add secret

### Passo 4: Atualizar Workflow

```yaml
      - name: Deploy to GitHub Pages
        if: github.ref == 'refs/heads/main' && github.event_name == 'push'
        uses: peaceiris/actions-gh-pages@v3
        with:
          deploy_key: ${{ secrets.DEPLOY_KEY }}
          publish_dir: ./
          cname: paco.dev
```

### Passo 5: Teste

```bash
git add .github/workflows/deploy.yml
git commit -m "fix: use deploy key"
git push origin main
```

**Vantagens:**
- ✅ Mais seguro (chave dedicada)
- ✅ Funciona com branch protection
- ✅ Sem usar GITHUB_TOKEN

---

## OPÇÃO 3: Usar Personal Access Token (PAT)

Se quer usar token pessoal.

### Passo 1: Gerar PAT no GitHub

GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic):
1. Generate new token
2. Nome: "gh-pages-deploy"
3. Expiration: 90 days (ou custom)
4. Scopes: 
   - ☑ repo (full control)
   - ☑ workflow
5. Generate token
6. **Copie o token** (só aparece uma vez!)

### Passo 2: Adicionar nos Secrets

Settings → Secrets and variables → Actions:
1. New repository secret
2. Nome: `GH_TOKEN`
3. Valor: Cole o token
4. Add secret

### Passo 3: Atualizar Workflow

```yaml
      - name: Deploy to GitHub Pages
        if: github.ref == 'refs/heads/main' && github.event_name == 'push'
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GH_TOKEN }}
          publish_dir: ./
          cname: paco.dev
```

### Passo 4: Teste

```bash
git add .github/workflows/deploy.yml
git commit -m "fix: use personal access token"
git push origin main
```

**Vantagens:**
- ✅ Mais controle
- ✅ Funciona com tudo
- ⚠️ Menos seguro (token pessoal)

---

## OPÇÃO 4: Remover Branch Protection Temporário

Se `main` está protegida:

Settings → Branches → Branch protection rules:
1. Selecione a rule de `main`
2. Disable/Delete temporariamente
3. Teste o deploy
4. Re-ativar a proteção se necessário

⚠️ Não recomendado para repositórios públicos

---

## RESUMO - Qual Escolher?

| Opção | Dificuldade | Segurança | Recomendação |
|-------|-----------|-----------|-------------|
| **1. GitHub Actions Deploy** | ⭐ Fácil | ⭐⭐⭐ Ótimo | ✅ MELHOR |
| **2. Deploy Key** | ⭐⭐ Médio | ⭐⭐⭐⭐⭐ Máxima | ✅ SEGURO |
| **3. Personal Access Token** | ⭐⭐ Médio | ⭐⭐ Baixa | ⚠️ Último recurso |
| **4. Remover Proteção** | ⭐ Fácil | ❌ Perigoso | ❌ NÃO FAÇA |

---

## 🎯 RECOMENDAÇÃO FINAL

**Comece com OPÇÃO 1 (GitHub Actions Deploy)**

É a mais simples e moderna:
1. Não precisa de chaves
2. Não precisa de tokens
3. Nativa do GitHub
4. Sem permissões adicionais

Siga esses passos:

1. Edite `.github/workflows/deploy.yml`
2. Substitua Deploy section por:
```yaml
      - name: Upload Pages artifact
        if: github.ref == 'refs/heads/main' && github.event_name == 'push'
        uses: actions/upload-pages-artifact@v3
        with:
          path: './.'

      - name: Deploy to GitHub Pages
        if: github.ref == 'refs/heads/main' && github.event_name == 'push'
        id: deployment
        uses: actions/deploy-pages@v2
```

3. Vá para Settings → Pages
4. Source: Selecione **GitHub Actions**
5. Teste com `git push`

---

## ⚡ SE NADA FUNCIONAR

1. Verifique se repositório é público
2. Verifique se GitHub Pages está habilitado
3. Veja os logs no GitHub Actions para mensagem de erro específica
4. Abra uma issue no repositório original do peaceiris/actions-gh-pages

---

**Qual opção prefere testar primeiro?** 🚀
