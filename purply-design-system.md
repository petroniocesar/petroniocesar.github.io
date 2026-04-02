# Purply — Design System Documentation
> Template SaaS Landing Page · purply.framer.website  
> Documentação pronta para colar em projetos e pedir para IA implementar.

---

## 1. Paleta de Cores

### Cores Primárias
| Token | Hex | Uso |
|---|---|---|
| `--color-brand-primary` | `#7C3AED` | Roxo principal — CTAs, destaques, ícones ativos |
| `--color-brand-secondary` | `#A78BFA` | Roxo claro — hovers, gradientes, badges |
| `--color-brand-accent` | `#C4B5FD` | Roxo suave — bordas de cards, separadores |

### Fundo & Superfícies
| Token | Hex | Uso |
|---|---|---|
| `--color-bg-base` | `#FFFFFF` | Fundo geral da página (light) |
| `--color-bg-surface` | `#F9F7FF` | Cards, seções alternadas, containers |
| `--color-bg-muted` | `#F3F0FF` | Inputs, chips, badges neutros |
| `--color-bg-overlay` | `rgba(124, 58, 237, 0.06)` | Glow de fundo sutil atrás de elementos hero |

### Texto
| Token | Hex | Uso |
|---|---|---|
| `--color-text-primary` | `#0F0A1E` | Headings principais |
| `--color-text-secondary` | `#4B4463` | Parágrafos, descrições |
| `--color-text-muted` | `#9089A8` | Labels, placeholders, metadados |
| `--color-text-on-brand` | `#FFFFFF` | Texto sobre botões/fundos roxo |

### Estados & Utilitários
| Token | Hex | Uso |
|---|---|---|
| `--color-border-default` | `#E8E0FF` | Bordas de cards e inputs |
| `--color-border-focus` | `#7C3AED` | Borda de input em foco |
| `--color-success` | `#22C55E` | Ícones de check em listas de features |
| `--color-badge-new` | `#7C3AED` | Badge "New" no topo do hero |

### Gradientes
```css
/* Hero background glow */
--gradient-hero: radial-gradient(ellipse 80% 60% at 50% -10%, rgba(124, 58, 237, 0.18) 0%, transparent 70%);

/* Botão primário */
--gradient-btn-primary: linear-gradient(135deg, #7C3AED 0%, #6D28D9 100%);

/* Separador decorativo */
--gradient-divider: linear-gradient(90deg, transparent, #C4B5FD, transparent);
```

---

## 2. Tipografia

### Família de Fontes
```css
--font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
/* Inter é a fonte padrão do Framer e corresponde ao visual do template */
```

### Escala de Tamanhos
| Token | Tamanho | Line-height | Peso | Uso |
|---|---|---|---|---|
| `--text-xs` | `12px` | `1.5` | 400 | Metadados, timestamps, captions |
| `--text-sm` | `14px` | `1.6` | 400 | Labels, badges, textos auxiliares |
| `--text-base` | `16px` | `1.7` | 400 | Corpo de texto, parágrafos |
| `--text-lg` | `18px` | `1.6` | 500 | Subtítulos de seção, quotes |
| `--text-xl` | `20px` | `1.5` | 600 | Títulos de card, preço |
| `--text-2xl` | `24px` | `1.4` | 600 | Títulos de subsection |
| `--text-3xl` | `32px` | `1.3` | 700 | Títulos H2 de seção |
| `--text-4xl` | `48px` | `1.2` | 700 | Títulos H1 mobile |
| `--text-5xl` | `64px` | `1.1` | `800` | Hero heading desktop |

### Pesos Utilizados
```css
--font-weight-regular: 400;
--font-weight-medium:  500;
--font-weight-semibold: 600;
--font-weight-bold:    700;
--font-weight-extrabold: 800;
```

### Padrões Tipográficos
```css
/* Hero Heading */
.heading-hero {
  font-size: clamp(48px, 7vw, 72px);
  font-weight: 800;
  line-height: 1.1;
  letter-spacing: -0.03em;
  color: var(--color-text-primary);
}

/* Section Heading (H2) */
.heading-section {
  font-size: clamp(28px, 4vw, 40px);
  font-weight: 700;
  line-height: 1.2;
  letter-spacing: -0.02em;
  color: var(--color-text-primary);
}

/* Section Subtitle */
.text-section-subtitle {
  font-size: 16px;
  font-weight: 400;
  line-height: 1.7;
  color: var(--color-text-secondary);
  max-width: 560px;
}

/* Badge / Label */
.text-label {
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--color-brand-primary);
}
```

---

## 3. Espaçamento — Grid de 8px

### Tokens de Espaço
```css
--space-1:  4px;   /* micro */
--space-2:  8px;   /* xs */
--space-3:  12px;  /* sm */
--space-4:  16px;  /* md */
--space-5:  24px;  /* lg */
--space-6:  32px;  /* xl */
--space-7:  40px;  /* 2xl */
--space-8:  48px;  /* 3xl */
--space-9:  64px;  /* 4xl */
--space-10: 80px;  /* 5xl */
--space-11: 96px;  /* 6xl */
--space-12: 128px; /* section */
```

### Aplicação por Contexto
| Contexto | Valor |
|---|---|
| Gap entre ícone e texto em botão | `8px` |
| Padding interno de botão (horizontal) | `24px` |
| Padding interno de botão (vertical) | `12px` |
| Padding interno de card | `32px` |
| Gap entre cards na grid | `24px` |
| Espaço entre seções da página | `96–128px` |
| Padding lateral do container (desktop) | `80px` |
| Padding lateral do container (mobile) | `16px` |
| Gap entre label e heading de seção | `12px` |
| Gap entre heading e parágrafo de seção | `16px` |

### Container / Layout Grid
```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-10); /* 80px desktop */
}

@media (max-width: 768px) {
  .container {
    padding: 0 var(--space-4); /* 16px mobile */
  }
}

/* Grid de Cards — 3 colunas */
.grid-3 {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-5); /* 24px */
}

@media (max-width: 1024px) {
  .grid-3 { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 640px) {
  .grid-3 { grid-template-columns: 1fr; }
}
```

---

## 4. Border Radius
```css
--radius-sm:   6px;   /* chips, badges pequenos */
--radius-md:  10px;   /* inputs, botões secundários */
--radius-lg:  16px;   /* cards de feature */
--radius-xl:  24px;   /* cards de pricing, containers grandes */
--radius-full: 9999px; /* botões pill, avatares, badges */
```

---

## 5. Sombras
```css
--shadow-card:    0 2px 12px rgba(124, 58, 237, 0.08);
--shadow-card-hover: 0 8px 32px rgba(124, 58, 237, 0.14);
--shadow-btn:     0 4px 16px rgba(124, 58, 237, 0.30);
--shadow-input-focus: 0 0 0 3px rgba(124, 58, 237, 0.20);
```

---

## 6. Componentes

### 6.1 Botões

#### Button Primary (CTA principal)
```html
<button class="btn-primary">Get Template</button>
```
```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);           /* 8px */
  padding: 12px 24px;
  background: var(--gradient-btn-primary);
  color: var(--color-text-on-brand);
  font-size: 15px;
  font-weight: 600;
  border: none;
  border-radius: var(--radius-full);
  box-shadow: var(--shadow-btn);
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.btn-primary:hover {
  transform: translateY(-1px);
  box-shadow: 0 6px 24px rgba(124, 58, 237, 0.40);
}
.btn-primary:active {
  transform: translateY(0);
}
```

#### Button Secondary (outline/ghost)
```html
<button class="btn-secondary">See Our Pricing</button>
```
```css
.btn-secondary {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);
  padding: 11px 22px;
  background: transparent;
  color: var(--color-text-primary);
  font-size: 15px;
  font-weight: 600;
  border: 1.5px solid var(--color-border-default);
  border-radius: var(--radius-full);
  cursor: pointer;
  transition: border-color 0.2s, background 0.2s;
}
.btn-secondary:hover {
  border-color: var(--color-brand-secondary);
  background: var(--color-bg-muted);
}
```

#### Button Text / Link
```css
.btn-link {
  display: inline-flex;
  align-items: center;
  gap: var(--space-1);
  background: none;
  border: none;
  color: var(--color-brand-primary);
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  text-decoration: underline;
  text-underline-offset: 3px;
}
```

---

### 6.2 Badge / Chip
```html
<span class="badge">New</span>
<span class="badge-section">Features</span>
```
```css
/* Badge inline (hero) */
.badge {
  display: inline-flex;
  align-items: center;
  padding: 4px 12px;
  background: var(--color-bg-muted);
  color: var(--color-brand-primary);
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.04em;
  border-radius: var(--radius-full);
  border: 1px solid var(--color-brand-accent);
}

/* Label de seção (ex: "Features", "Benefits") */
.badge-section {
  display: inline-block;
  padding: 4px 14px;
  background: var(--color-bg-muted);
  color: var(--color-brand-primary);
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  border-radius: var(--radius-full);
  border: 1px solid var(--color-brand-accent);
  margin-bottom: var(--space-3);
}
```

---

### 6.3 Cards

#### Feature Card (ícone + título + descrição)
```html
<div class="card-feature">
  <div class="card-feature__icon"><!-- SVG icon --></div>
  <h3 class="card-feature__title">Instant Analytics Dashboard</h3>
  <p class="card-feature__desc">View critical data in real time and optimize every decision effortlessly.</p>
</div>
```
```css
.card-feature {
  background: var(--color-bg-surface);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-xl);      /* 24px */
  padding: var(--space-6);             /* 32px */
  display: flex;
  flex-direction: column;
  gap: var(--space-4);                 /* 16px */
  transition: box-shadow 0.25s ease, transform 0.25s ease;
}
.card-feature:hover {
  box-shadow: var(--shadow-card-hover);
  transform: translateY(-3px);
}
.card-feature__icon {
  width: 48px;
  height: 48px;
  background: var(--color-bg-muted);
  border-radius: var(--radius-md);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-brand-primary);
}
.card-feature__title {
  font-size: 18px;
  font-weight: 600;
  color: var(--color-text-primary);
  line-height: 1.4;
}
.card-feature__desc {
  font-size: 14px;
  color: var(--color-text-secondary);
  line-height: 1.6;
}
```

#### Pricing Card
```html
<div class="card-pricing card-pricing--featured">
  <span class="card-pricing__plan">Pro Plan</span>
  <p class="card-pricing__tagline">Perfect for Businesses</p>
  <div class="card-pricing__price">
    <span class="price-amount">$129</span>
    <span class="price-period">Monthly Subscription</span>
  </div>
  <button class="btn-primary">Get Started</button>
  <ul class="card-pricing__features">
    <li>Team collaboration</li>
    <li>Unlimited dashboards</li>
  </ul>
</div>
```
```css
.card-pricing {
  background: var(--color-bg-surface);
  border: 1.5px solid var(--color-border-default);
  border-radius: var(--radius-xl);
  padding: var(--space-6);            /* 32px */
  display: flex;
  flex-direction: column;
  gap: var(--space-5);               /* 24px */
}
.card-pricing--featured {
  background: var(--color-brand-primary);
  border-color: transparent;
  color: #fff;
  box-shadow: var(--shadow-btn);
}
.card-pricing__plan {
  font-size: 12px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-brand-accent);
}
.price-amount {
  font-size: 40px;
  font-weight: 800;
  color: var(--color-text-primary);
}
.card-pricing--featured .price-amount {
  color: #fff;
}
.price-period {
  font-size: 13px;
  color: var(--color-text-muted);
  display: block;
}
.card-pricing__features {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: var(--space-3);              /* 12px */
}
.card-pricing__features li {
  font-size: 14px;
  color: var(--color-text-secondary);
  display: flex;
  align-items: center;
  gap: var(--space-2);
}
.card-pricing__features li::before {
  content: "✓";
  color: var(--color-success);
  font-weight: 700;
}
```

#### Testimonial Card
```css
.card-testimonial {
  background: var(--color-bg-surface);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-xl);
  padding: var(--space-6);
  display: flex;
  flex-direction: column;
  gap: var(--space-4);
}
.card-testimonial__quote {
  font-size: 15px;
  line-height: 1.7;
  color: var(--color-text-secondary);
  font-style: italic;
}
.card-testimonial__author {
  display: flex;
  align-items: center;
  gap: var(--space-3);
}
.card-testimonial__avatar {
  width: 40px;
  height: 40px;
  border-radius: var(--radius-full);
  object-fit: cover;
}
.card-testimonial__name {
  font-size: 14px;
  font-weight: 600;
  color: var(--color-text-primary);
}
.card-testimonial__role {
  font-size: 12px;
  color: var(--color-text-muted);
}
```

---

### 6.4 Inputs & Forms

#### Input de Email (newsletter/CTA)
```html
<div class="input-group">
  <input class="input" type="email" placeholder="Enter your email" />
  <button class="btn-primary">Subscribe</button>
</div>
```
```css
.input {
  width: 100%;
  padding: 12px 16px;
  font-size: 15px;
  color: var(--color-text-primary);
  background: var(--color-bg-base);
  border: 1.5px solid var(--color-border-default);
  border-radius: var(--radius-full);
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}
.input::placeholder {
  color: var(--color-text-muted);
}
.input:focus {
  border-color: var(--color-border-focus);
  box-shadow: var(--shadow-input-focus);
}
.input-group {
  display: flex;
  gap: var(--space-2);
  align-items: center;
  max-width: 480px;
}
```

---

### 6.5 Navbar
```css
.navbar {
  position: sticky;
  top: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--space-4) var(--space-10);  /* 16px 80px */
  background: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--color-border-default);
}
.navbar__logo {
  font-size: 20px;
  font-weight: 800;
  color: var(--color-brand-primary);
  letter-spacing: -0.02em;
}
.navbar__links {
  display: flex;
  align-items: center;
  gap: var(--space-6);               /* 32px */
  list-style: none;
}
.navbar__link {
  font-size: 14px;
  font-weight: 500;
  color: var(--color-text-secondary);
  text-decoration: none;
  transition: color 0.2s;
}
.navbar__link:hover {
  color: var(--color-brand-primary);
}
```

---

### 6.6 FAQ Accordion
```css
.faq-item {
  border-bottom: 1px solid var(--color-border-default);
  padding: var(--space-5) 0;        /* 24px 0 */
}
.faq-item__question {
  font-size: 16px;
  font-weight: 600;
  color: var(--color-text-primary);
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.faq-item__answer {
  font-size: 15px;
  line-height: 1.7;
  color: var(--color-text-secondary);
  margin-top: var(--space-3);       /* 12px */
  max-width: 680px;
}
```

---

### 6.7 Comparison Table (Purply vs Others)
```css
.comparison-table {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-5);
  background: var(--color-bg-surface);
  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-xl);
  overflow: hidden;
}
.comparison-col {
  padding: var(--space-6);
}
.comparison-col--brand {
  background: var(--color-brand-primary);
  color: #fff;
}
.comparison-col__title {
  font-size: 16px;
  font-weight: 700;
  margin-bottom: var(--space-5);
}
.comparison-col__item {
  display: flex;
  align-items: flex-start;
  gap: var(--space-2);
  font-size: 14px;
  line-height: 1.6;
  padding: var(--space-2) 0;
}
```

---

## 7. Animações & Transições

```css
/* Padrão global */
--transition-fast:   0.15s ease;
--transition-base:   0.25s ease;
--transition-slow:   0.4s ease;

/* Fade-up (para seções ao entrar na viewport) */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}
.animate-fade-up {
  animation: fadeUp 0.5s var(--transition-base) both;
}

/* Ticker/marquee horizontal */
@keyframes marquee {
  from { transform: translateX(0); }
  to   { transform: translateX(-50%); }
}
.ticker {
  display: flex;
  overflow: hidden;
}
.ticker__track {
  display: flex;
  gap: var(--space-6);
  animation: marquee 20s linear infinite;
  white-space: nowrap;
}
```

---

## 8. Guia de Uso para IA

> Cole este bloco no início do prompt ao pedir implementação:

```
Implemente usando o Design System do Purply:
- Variáveis CSS definidas com prefixo --color-, --space-, --text-, --radius-, --shadow-
- Fonte: Inter (Google Fonts)
- Grid de 8px para todos os espaçamentos
- Background padrão: #FFFFFF com superfícies em #F9F7FF
- Cor brand: #7C3AED (roxo)
- Bordas arredondadas com --radius-xl (24px) para cards, --radius-full para botões
- Botão primário: gradiente roxo, pill shape, sombra roxa
- Botão secundário: outline pill, sem preenchimento
- Cards com hover: translateY(-3px) + sombra roxa suave
- Sections separadas por 96–128px
- Container max-width: 1200px, padding lateral 80px (16px mobile)
- Sempre usar tokens CSS, nunca valores hardcoded
```

---

*Design System extraído e documentado a partir da análise visual do template Purply (purply.framer.website). Criado por Peter Design.*
