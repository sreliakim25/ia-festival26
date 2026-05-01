# AI Festival 2026 — Guia Estratégico dos Palestrantes

Landing page interativa e PWA com o guia estratégico dos 20 palestrantes confirmados no **AI Festival 2026** (StartSe · 13 e 14 de maio · Pro Magno, São Paulo).

## Funcionalidades

- **Countdown** em tempo real até o evento
- **Grid de palestrantes** com busca instantânea e filtros por categoria (Big Tech, Startup, Finanças, Indústria, Academia, Consultoria, Mídia)
- **Modal detalhado** por speaker com:
  - Biografia resumida
  - Tópicos que estão abordando em 2025-2026
  - 4 perguntas estratégicas calibradas (com botão **Copiar** para levar ao evento)
- **PWA (Progressive Web App)** — instale no celular para acesso offline
- Dark mode, design responsivo, animações suaves

## Speakers

| # | Nome | Empresa | Categoria |
|---|------|---------|-----------|
| 1 | Henrique Savelli | Anthropic | Big Tech |
| 2 | Paul F. Accornero | Harvard / The AI Praxis | Consultoria |
| 3 | Peter Danenberg | Google DeepMind | Big Tech |
| 4 | Ana Trišović | MIT CSAIL | Academia |
| 5 | Justin Liu | Genspark | Startup |
| 6 | Leonardo Zappa | Glean | Startup |
| 7 | Felipe Blanes | Amazon AGI Labs | Big Tech |
| 8 | Jose Caodaglio | ColmeIA | Startup |
| 9 | Rafael Siqueira | McKinsey | Consultoria |
| 10 | Rafael Cavalcanti | Bradesco | Finanças |
| 11 | Carlos Octavio | Globo | Mídia |
| 12 | Celso Camilo | UFG / CEIA | Academia |
| 13 | Marcelo Braga | IBM Brasil | Big Tech |
| 14 | Leandro Vieira | Oracle | Big Tech |
| 15 | Alexandre Leão | Crescera Capital | Finanças |
| 16 | Priscyla Laham | Microsoft Brasil | Big Tech |
| 17 | Isabella Piratininga | iFood | Startup |
| 18 | André Petenussi | Localiza&Co | Indústria |
| 19 | Cristina Cestari | Volkswagen | Indústria |
| 20 | Cristiano Kruel | StartSe | Consultoria |

## Estrutura do Projeto

```
/
├── index.html          # App completo (HTML + CSS + JS em arquivo único)
├── manifest.json       # PWA manifest
├── sw.js               # Service worker (cache offline)
├── vercel.json         # Configuração de deploy Vercel
├── icons/
│   ├── icon-192.svg    # Ícone PWA 192x192
│   ├── icon-512.svg    # Ícone PWA 512x512
│   └── apple-touch-icon.svg  # Ícone iOS
└── README.md
```

## Rodando Localmente

Qualquer servidor HTTP estático funciona. Exemplos:

```bash
# Python
python3 -m http.server 3000

# Node.js (npx)
npx serve .

# VS Code — extensão Live Server
# Clique com botão direito em index.html → "Open with Live Server"
```

Acesse `http://localhost:3000`.

> **Nota:** O service worker só registra em `localhost` ou HTTPS. Para testar o PWA completo, use o deploy na Vercel.

## Deploy na Vercel

### Via Vercel CLI

```bash
npm i -g vercel
vercel
```

### Via GitHub (recomendado)

1. Faça push para este repositório
2. Acesse [vercel.com](https://vercel.com) → **Add New Project**
3. Importe o repositório `ia-festival26`
4. Clique em **Deploy** — a Vercel detecta o projeto estático automaticamente

O `vercel.json` já configura:
- Headers corretos para o service worker (`no-cache`)
- Cache longo para ícones
- Security headers (X-Frame-Options, X-XSS-Protection)
- Rewrite para SPA

### Domínio Personalizado

Após o deploy, em **Project Settings → Domains**, adicione seu domínio.

## PWA — Instalar no Celular

**Android (Chrome):**
- Acesse o site → banner "Instalar app" aparece automaticamente
- Ou: menu ⋮ → "Adicionar à tela inicial"

**iOS (Safari):**
- Acesse o site → botão Compartilhar → "Adicionar à Tela de Início"

O app funciona **offline** após a primeira visita (service worker cacheia todos os assets).

## Tech Stack

- **HTML5 + CSS3 + JavaScript** vanilla — zero dependências
- **CSS Custom Properties** para tema consistente
- **CSS Grid + Flexbox** para layout responsivo
- **Service Worker** (Cache API) para offline
- **Web App Manifest** para instalação como PWA

## Licença

Conteúdo educacional para preparação ao AI Festival 2026. Informações baseadas em fontes públicas dos palestrantes.
