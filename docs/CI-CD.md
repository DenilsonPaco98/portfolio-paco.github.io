# CI/CD Pipeline Documentation

## Overview
Este projeto usa **GitHub Actions** para automatizar o build e deploy da página do portfólio.

## Workflow: Deploy Portfolio

### Trigger
- **Push em `main`**: Deploy para produção (GitHub Pages)
- **Push em `develop`**: Build de staging (ambiente de desenvolvimento)
- **Pull Requests**: Validações de lint

### Steps

1. **Checkout Code**
   - Faz checkout do repositório

2. **Setup Node.js**
   - Configura Node.js v20

3. **Install Dependencies**
   - Instala dependências do `package.json`

4. **Lint HTML**
   - Valida HTML com `html-validate`
   - Não falha o workflow (|| true)

5. **Deploy to GitHub Pages**
   - Ramo: `main`
   - Usa `peaceiris/actions-gh-pages`
   - Publica em `paco.dev`

### Ambiente de Desenvolvimento

#### Setup Local
```bash
# Clone o repositório
git clone https://github.com/portfolio-paco/portfolio-paco.github.io.git
cd portfolio-paco.github.io

# Crie branch de desenvolvimento
git checkout -b develop

# Instale dependências
npm install

# Inicie servidor local
npm start
```

O servidor rodará em `http://localhost:8000`

#### Git Flow
```
main (produção) ← Pull Request ← develop (staging)
```

1. Trabalhe no branch `develop`
2. Teste localmente
3. Faça Push para `develop`
4. CI/CD valida automaticamente
5. Abra PR para `main`
6. Merge e deploy automático

### Variáveis de Ambiente

Nenhuma variável secreta necessária atualmente. O `GITHUB_TOKEN` é injetado automaticamente.

### Monitoramento

- Logs visíveis em: **Actions → Deploy Portfolio → Runs**
- Status do deploy no README do repositório

### Troubleshooting

**Deploy não está funcionando?**
- Verifique se `GITHUB_TOKEN` está habilitado nas settings
- Confirm branch protection rules
- Verifique logs em Actions

**HTML Lint falhando?**
- O workflow continua mesmo com falhas de lint
- Corrija warnings manualmente

---

## Estrutura de Ambientes

### Produção (main)
- Url: `paco.dev` / GitHub Pages
- Deploy automático após merge
- Branch protegido

### Staging (develop)
- Ambiente de desenvolvimento
- Testes antes de merge para main
- Branch para todas as features
