# 📚 Roadmap de Certificações AWS

## Estrutura do Roadmap

Seu portfólio agora possui uma **seção completa de Roadmap** mostrando:

- ✅ **Certificações Completadas** (com progresso 100%)
- ⏱ **Em Progresso** (mostra % de conclusão)
- ▶ **Próximas** (planejadas)
- ◆ **Planejadas** (futuro)

## Certificações Incluídas

### Nível Foundational
- **AWS Cloud Practitioner (CLF-C02)** - ✓ Completado

### Nível Associate
- **AWS Solutions Architect (SAA-C03)** - ✓ Completado
- **AWS Machine Learning Associate (MLA-C01)** - ✓ Completado
- **AWS Developer Associate (DVA-C02)** - ▶ Próximo (15% progresso)

### Nível Specialty
- **AWS Data Analytics Specialist (DAS-C01)** - ⏱ Em Progresso (65%)

### Nível Professional
- **AWS DevOps Professional (DOP-C02)** - ◆ Planejado (0%)

## Como Personalizar o Roadmap

### Atualizar Progresso de uma Certificação

Localize a `<div class="roadmap-card">` correspondente no `index.html` e:

1. **Altere o status do badge:**
   ```html
   <!-- Mude a classe -->
   <span class="roadmap-badge completed">✓ Completado</span>
   <span class="roadmap-badge in-progress">⏱ Em Progresso</span>
   <span class="roadmap-badge upcoming">▶ Próximo</span>
   ```

2. **Atualize a percentagem:**
   ```html
   <div class="progress-label">
     <span>Progresso</span>
     <span>75%</span>  <!-- Mude para seu % -->
   </div>
   <div class="progress-bar">
     <div class="progress-fill" style="width: 75%"></div>  <!-- % aqui também -->
   </div>
   ```

3. **Atualize as datas:**
   ```html
   <div class="roadmap-timeline">
     <div class="roadmap-timeline-item">
       <strong>Aprovado:</strong> Jan 2025
     </div>
   </div>
   ```

### Adicionar Nova Certificação

Copie este template e adicione ao `.roadmap-grid`:

```html
<div class="roadmap-card">
  <div class="roadmap-header">
    <div>
      <div class="roadmap-level">Nível Category</div>
      <div class="roadmap-name">Certificação Name</div>
      <div class="roadmap-code">CODE-01</div>
    </div>
    <span class="roadmap-badge upcoming">▶ Próximo</span>
  </div>
  <div class="progress-section">
    <div class="progress-label">
      <span>Progresso</span>
      <span>0%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 0%"></div>
    </div>
  </div>
  <div class="roadmap-topics">
    <strong>Tópicos principais:</strong>
    Topic1 · Topic2 · Topic3 · Topic4
  </div>
  <div class="roadmap-timeline">
    <div class="roadmap-timeline-item">
      <strong>Início:</strong> Data
    </div>
    <div class="roadmap-timeline-item">
      <strong>Meta:</strong> Data
    </div>
  </div>
</div>
```

## Status Badges Disponíveis

| Badge | Classe CSS | Significado |
|-------|-----------|-------------|
| ✓ Completado | `completed` | Certificação obtida |
| ⏱ Em Progresso | `in-progress` | Estudando ativamente |
| ▶ Próximo | `upcoming` | Próxima na fila |
| ◆ Planejado | `upcoming` | Futuro planejado |

## Cores do Tema

- **Completado**: Cyan (`var(--accent)`)
- **Em Progresso**: Orange (`var(--accent2)`)
- **Upcoming**: Muted Gray (`var(--muted)`)

## Dicas de Organização

1. **Mantenha a ordem lógica**: Foundational → Associate → Specialty → Professional
2. **Atualize regularmente**: A cada semana atualize o progresso
3. **Use % reais**: 0%, 25%, 50%, 75%, 100%
4. **Incluir timeline**: Mostre quando começou e quando espera terminar

## Animações

Todos os cards possuem:
- ✨ Fade-in ao scroll
- 🎨 Hover effect (border cyan)
- 📱 Responsivo (mobile/tablet/desktop)

Os cards são observados pelo Intersection Observer e aparecem com delay quando entram na viewport!

---

**Próx Step**: Comitar mudanças e fazer push para `develop`, depois abrir PR para `main` para deploy automático! 🚀
