# 🚀 Portfolio - Denilson Paco Quispe

**Data Engineer | Cloud Architect | AWS Certified**

Portfolio profissional com CI/CD automatizado e roadmap de certificações.

🌐 **Live**: [paco.dev](https://paco.dev)

---

## 📋 Seções

- **👤 Hero**: Apresentação pessoal e call-to-action
- **💼 Experiência**: Timeline com histórico profissional
- **⚙️ Skills**: Stack técnica organizado por categorias
- **🏆 Certificações**: AWS certifications com badges
- **📚 Roadmap**: Plano de estudos com barra de progresso
- **📞 Contato**: Links para redes profissionais

---

## 🏗️ Arquitetura

```
portfolio-paco.github.io/
├── .github/
│   └── workflows/
│       └── deploy.yml          # CI/CD Pipeline
├── docs/
│   ├── CI-CD.md               # Documentação CI/CD
│   └── ROADMAP.md             # Guia do Roadmap
├── index.html                 # Página principal
├── package.json               # Dependências
└── README.md                  # Este arquivo
```

---

## 🚀 CI/CD Automático

### Workflow: Deploy Portfolio

**Triggers:**
- Push em `main` → Deploy para produção (GitHub Pages)
- Push em `develop` → Build de staging
- Pull Requests → Validações de lint

**Steps:**
1. ✅ Checkout code
2. 📦 Setup Node.js
3. 🔍 Lint HTML
4. 🚀 Deploy automático

Ver: [docs/CI-CD.md](docs/CI-CD.md)

---

## 📚 Roadmap de Certificações

Acompanhe seu progresso nas certificações AWS com:
- ✅ Certificações completadas
- ⏱ Estudos em progresso
- ▶ Próximas certificações
- 📊 Barra de progresso visual

**Certificações Atuais:**
- ✓ AWS Cloud Practitioner (CLF-C02)
- ✓ AWS Solutions Architect Associate (SAA-C03)
- ✓ AWS Machine Learning Associate (MLA-C01)
- ⏱ AWS Data Analytics Specialist (DAS-C01) - 65%
- ▶ AWS Developer Associate (DVA-C02) - Próx

Ver: [docs/ROADMAP.md](docs/ROADMAP.md) para personalizar

---

## 🛠️ Desenvolvimento Local

### Setup

```bash
git clone https://github.com/portfolio-paco/portfolio-paco.github.io.git
cd portfolio-paco.github.io

# Crie branch de desenvolvimento
git checkout -b develop

# Instale dependências (opcional)
npm install
```

### Rodar Localmente

```bash
npm start
# Abre em http://localhost:8000
```

### Git Flow

```
main (produção)
  ↑
  └─ Pull Request
      ↑
    develop (staging)
```

1. Trabalhe no branch `develop`
2. Teste localmente
3. Faça Push e abra PR para `main`
4. Deploy automático após merge

---

## 📝 Customizar

### Atualizar Info Pessoal

Edite no `index.html`:
- Nome, título, descrição (section hero)
- Experiência (section experiência)
- Skills (section skills)
- Certificações (section certs)

### Atualizar Roadmap

Ver [docs/ROADMAP.md](docs/ROADMAP.md) para:
- Adicionar novas certificações
- Atualizar progresso
- Modificar status

---

## 🎨 Design & Tema

**Paleta:**
- Accent (Cyan): `#00d4ff`
- Accent2 (Orange): `#ff6b35`
- Background: `#0a0a0a`
- Texto: `#f0f0f0`

**Fontes:**
- Headings: `Syne` (Google Fonts)
- Mono/Code: `DM Mono` (Google Fonts)

---

## 📊 Performance

- Zero frameworks (HTML/CSS/JS puro)
- Otimizado para mobile
- Lazy loading via Intersection Observer
- Smooth scrolling

---

## 📄 Licença

MIT - Sinta-se livre para usar este template como base!

---

## 💬 Contato

- 💼 LinkedIn: [denilson-paco-24b629181](https://linkedin.com/in/denilson-paco-24b629181)
- 📧 Email: Confira no portfólio
- 🔗 Portfolio: [paco.dev](https://paco.dev)

---

**Última atualização:** Março 2025

