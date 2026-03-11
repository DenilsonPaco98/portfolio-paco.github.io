# 📚 Trilhas de Estudo - Documentação

## Visão Geral

A seção de **Trilhas de Estudo** apresenta 4 certificações AWS com detalhes completos:

1. **AWS Solutions Architect Associate (SAA-C03)** ✓ Completado
2. **AWS Cloud Practitioner (CLF-C02)** ✓ Completado
3. **AWS Machine Learning Associate (MLA-C01)** ✓ Completado
4. **AWS AI Practitioner (AWS-AI-C01)** ⏱ Próximo

---

## 🏗️ Estrutura de cada Trilha

### Componentes Visuais

Cada cartão de trilha possui:

```
┌─────────────────────────────────────┐
│ 🏗️ Solutions Architect              │
│ SAA-C03                             │
│                                     │
│ Domine o design de arquiteturas ... │
│                                     │
│ 📚 Módulos Principais               │
│  • EC2 & Compute Services           │
│  • VPC & Networking                 │
│  • RDS & Databases                  │
│  • S3 & Storage                     │
│  • Lambda & Serverless              │
│  • Security & IAM                   │
│  • Disaster Recovery                │
│                                     │
│ ⏱ 6-8 semanas | 40-50 horas        │
│ ✓ COMPLETADO                        │
└─────────────────────────────────────┘
```

### Elementos

1. **Ícone & Título**
   - Emoji representativo
   - Nível (Foundational, Associate, etc)
   - Nome da certificação
   - Código oficial (SAA-C03, etc)

2. **Descrição**
   - 1-2 linhas sobre o que você aprende

3. **Módulos Principais**
   - Lista de 5-7 tópicos principais
   - Cada um com ícone visual (▸)

4. **Duração & Dificuldade**
   - Tempo estimado de estudo
   - Status (Completado, Próximo, etc)

---

## 🧠 Mapa Mental - Jornada AWS

Visual que mostra a progressão:

```
Fundamentos → Arquitetura → Especialização → IA Generativa
(Básico)    (Intermediário) (Avançado)      (Novo)
```

Cada nó do mapa:
- Representa um estágio da jornada
- Mostra o nível de dificuldade
- Conectado com setas

---

## 🎨 Personalizando as Trilhas

### Adicionar nova Trilha

Copie este template no `index.html` dentro de `.trails-container`:

```html
<div class="trail-card">
  <div class="trail-header">
    <div class="trail-icon">EMOJI</div>
    <div class="trail-info">
      <div class="trail-level">Nível LEVEL</div>
      <h3>Nome Certificação</h3>
      <div class="trail-code">CODIGO-XX</div>
    </div>
  </div>
  
  <p class="trail-description">
    Descrição breve sobre a certificação...
  </p>

  <div class="trail-modules">
    <h4>📚 Módulos Principais</h4>
    <div class="modules-list">
      <div class="module-item">Módulo 1</div>
      <div class="module-item">Módulo 2</div>
      <div class="module-item">Módulo 3</div>
      <div class="module-item">Módulo 4</div>
      <div class="module-item">Módulo 5</div>
    </div>
  </div>

  <div class="trail-duration">⏱ X-Y semanas | ZZ-WW horas</div>
  <span class="trail-difficulty">STATUS</span>
</div>
```

### Alternar Status

Mude a classe de `trail-difficulty`:

```html
<!-- Completado -->
<span class="trail-difficulty">✓ COMPLETADO</span>

<!-- Em Progresso -->
<span class="trail-difficulty">⏱ EM PROGRESSO</span>

<!-- Próximo -->
<span class="trail-difficulty">▶ PRÓXIMO</span>

<!-- Planejado -->
<span class="trail-difficulty">◆ PLANEJADO</span>
```

### Customizar Ícones

Use qualquer emoji:

```html
<!-- Exemplos -->
<div class="trail-icon">🏗️</div>   <!-- Arquitetura -->
<div class="trail-icon">☁️</div>   <!-- Cloud -->
<div class="trail-icon">🤖</div>   <!-- Machine Learning -->
<div class="trail-icon">✨</div>   <!-- IA Generativa -->
<div class="trail-icon">📊</div>   <!-- Data Analytics -->
<div class="trail-icon">🔧</div>   <!-- DevOps -->
<div class="trail-icon">🛡️</div>   <!-- Security -->
```

---

## 📱 Responsividade

A seção é 100% responsiva:

- **Desktop**: Grid com 4 colunas
- **Tablet**: Grid com 2 colunas
- **Mobile**: 1 coluna (stack)

Todos os elementos se adaptam automaticamente.

---

## ✨ Animações

### Cards de Trilha
- Fade-in ao scroll (Intersection Observer)
- Hover effect com elevação
- Gradient background dinâmico

### Mapa Mental
- Nós com border accent
- Hover com scale-up
- Glow effect ao passar mouse

---

## 🔄 Atualizar Trilhas

### Quando completar uma certificação

1. Mude a classe de `trail-difficulty`:
   ```html
   <!-- De -->
   <span class="trail-difficulty">▶ PRÓXIMO</span>
   
   <!-- Para -->
   <span class="trail-difficulty">✓ COMPLETADO</span>
   ```

2. Ordene os cards na seção (completos primeiro)

3. Atualize o `trail-difficulty` da próxima

4. Git push → Deploy automático em 2 minutos!

---

## 🎯 Boas Práticas

1. **Módulos Realistas**
   - Liste 5-7 tópicos principais
   - Seja específico
   - Ordem lógica de aprendizado

2. **Duração Acurada**
   - Baseie em experiência real
   - Inclua tempo de prática
   - Tempo de prova

3. **Descrições Concisas**
   - 1-2 linhas máximo
   - Foco em benefício
   - Específico à certificação

4. **Ícones Representativos**
   - Use emoji que faça sentido
   - Consistência visual
   - Fácil de reconhecer

---

## 📊 Exemplo Completo

```html
<!-- AWS DevOps Professional -->
<div class="trail-card">
  <div class="trail-header">
    <div class="trail-icon">🔧</div>
    <div class="trail-info">
      <div class="trail-level">Nível Professional</div>
      <h3>DevOps Engineer</h3>
      <div class="trail-code">DOP-C02</div>
    </div>
  </div>
  
  <p class="trail-description">
    Mastermind em CI/CD, automação e infraestrutura. Crie pipelines robuustos e gerencie deployments em escala.
  </p>

  <div class="trail-modules">
    <h4>📚 Módulos Principais</h4>
    <div class="modules-list">
      <div class="module-item">CodePipeline & CodeBuild</div>
      <div class="module-item">Infrastructure as Code</div>
      <div class="module-item">CloudFormation & Terraform</div>
      <div class="module-item">Container Orchestration</div>
      <div class="module-item">Monitoring & Logging</div>
      <div class="module-item">Performance Optimization</div>
      <div class="module-item">Cost Optimization</div>
    </div>
  </div>

  <div class="trail-duration">⏱ 10-12 semanas | 60-80 horas</div>
  <span class="trail-difficulty">▶ PRÓXIMO</span>
</div>
```

---

## 🚀 Deploy

Depois de atualizar:

```bash
git add index.html
git commit -m "feat: update study trails"
git push origin main
```

Deploy automático em 1-2 minutos! ✅

---

**Próximas adições:**
- AWS Data Analytics Specialist
- AWS Security Specialty
- AWS Advanced Networking Specialty
