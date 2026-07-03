# Contexto do Projeto: CerraCare

## Visão Geral
CerraCare é um MVP (Minimum Viable Product) de um Prontuário Eletrônico e Sistema de Gestão de Cuidadoras. O foco atual do projeto é ser uma aplicação web rápida, moderna, com design mobile-first e que possa ser hospedada de forma estática no GitHub Pages como um PWA (Progressive Web App).

## Stack Tecnológica Utilizada
- **Linguagens**: HTML5, JavaScript Vanilla (ES6+)
- **Estilização**: Tailwind CSS (via CDN) e CSS personalizado para animações e componentes específicos (como os toggles).
- **Ícones**: FontAwesome
- **Armazenamento de Dados**: `localStorage` (persistência de dados no navegador, simulando um banco de dados).

## Histórico de Ações
1. **Desenvolvimento do MVP (Single-Page Application)**:
   - Criação de toda a estrutura no arquivo `index.html`.
   - Implementação do design responsivo com cores primárias em tons de azul e verde (Emerald/Sky).
2. **Deploy Inicial**:
   - Inicialização do repositório Git local.
   - Sincronização (`git pull rebase` e `git push`) para o repositório remoto no GitHub (`https://github.com/renato0503/CerraCare`).

## Módulos Presentes no MVP
- **Autenticação Simulada**: Login simples baseado no nome da cuidadora para assinatura de turno.
- **Prontuário (Registro de Rotina)**: 
  - Registro de Sinais Vitais (P.A., FC, Temperatura, Sat. O2).
  - Rotina de cuidados via Toggles (Alimentação, Medicação, Diurese/Evacuação).
  - Área de texto para relatório do plantão e qualidade do sono.
- **Histórico (Passagem de Plantão)**:
  - Timeline lendo os registros armazenados localmente e renderizando cards de forma cronológica reversa (mais recentes primeiro) contendo os dados do plantão.
- **Check-in / Geolocalização**:
  - Simulação de ponto/presença capturando as coordenadas via API nativa do navegador (`navigator.geolocation`) e registrando a hora exata da batida do ponto.
