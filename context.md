# Contexto do Projeto: CerraCare

## Visão Geral
CerraCare é um MVP (Minimum Viable Product) de um Prontuário Eletrônico e Sistema de Gestão de Cuidadoras. O foco atual do projeto é ser uma aplicação web rápida, moderna, com design mobile-first e que possa ser hospedada de forma estática no GitHub Pages como um PWA (Progressive Web App).

## Stack Tecnológica Utilizada
- **Linguagens**: HTML5, JavaScript Vanilla (ES6+)
- **Estilização**: Tailwind CSS (via CDN) e CSS personalizado para animações e componentes específicos (como os toggles).
- **Ícones**: FontAwesome
- **Armazenamento de Dados**: `localStorage` (persistência principal) e `IndexedDB` (fotos e fila de sincronização).
- **PWA**: `manifest.json`, `icon.svg` e `service-worker.js`.
- **Bibliotecas Externas**: jsPDF (via CDN) para exportação de relatórios PDF.
- **APIs Nativas**: Web Speech API (reconhecimento de voz), Geolocation API, Canvas API (assinatura digital).

## Deploy
- **GitHub Pages**: `https://renato0503.github.io/CerraCare/`
- **Repositório**: `https://github.com/renato0503/CerraCare`

## Módulos Presentes no MVP

### App da Cuidadora (`index.html`)
- **Autenticação Simulada**: Login simples baseado no nome da cuidadora para assinatura de turno.
- **Prontuário (Registro de Rotina)**:
  - Sinais Vitais (P.A., FC, Temperatura, Sat. O2) com validações rigorosas.
  - Escala de Dor (0-5) e Humor (5 emojis selecionáveis).
  - Rotina de cuidados via Toggles (Alimentação, Medicação, Diurese/Evacuação).
  - Checklist dinâmico de medicações (gerenciado pelo Admin).
  - Quadro de Horários de Medicação com alertas visuais (futuro/atual/atrasado).
  - Balanço Hídrico com botões de adição rápida e barra de progresso.
  - Relatório por Voz (Speech-to-Text via Web Speech API).
  - Captura de Fotos (armazenadas no IndexedDB).
  - Assinatura Digital via Canvas (touch/mouse).
- **Histórico (Passagem de Plantão)**:
  - Timeline cronológica reversa com cards contendo vitais, rotina, dor/humor, hidratação.
  - Botão de compartilhamento via WhatsApp com texto formatado.
- **Check-in / Geolocalização**:
  - Captura de coordenadas via `navigator.geolocation`.
  - Link para visualização no Google Maps.
- **Controle de Estoque**:
  - Visualização de itens cadastrados com indicadores coloridos (normal/baixo/crítico).
  - Botões de retirada rápida (-1, -2, -5) e reposição.
  - Log de movimentações.

### Painel Admin (`admin.html`)
- **Dashboard**: Total de registros, cuidadoras ativas, alertas (PA/Febre/Estoque), pendentes de sync.
- **CRUD de Registros**: Tabela com edição/exclusão, modal de formulário completo.
- **Gerenciador de Medicações**: Cadastro da lista de remédios para checklist da cuidadora.
- **Horários de Medicação**: Cadastro de nome + horários (ex: 08:00, 20:00).
- **Controle de Estoque**: Cadastro de itens, quantidades, unidades e thresholds de alerta.
- **Gráfico de Dor/Humor**: Barras dos últimos 10 registros com emojis.
- **Exportação PDF**: Geração de relatório A4 com jsPDF.
- **Fila de Sincronização**: Indicador de itens pendentes no IndexedDB.
- **Senha Configurável**: Senha do admin armazenada no localStorage, alterável via interface.

### PWA
- `manifest.json` com ícone SVG, theme-color, modo standalone.
- `service-worker.js` com cache de `index.html`, `admin.html`, `icon.svg` e `manifest.json`.
