# Matriz Brasileira de Fraudes Financeiras

Projeto comunitário e independente para documentar táticas e técnicas de fraudes financeiras observadas no Brasil.

O objetivo é criar uma base de conhecimento operacional, inspirada por frameworks como ATT&CK e Fight Fraud Framework, mas com foco local em golpes envolvendo PIX, boleto, WhatsApp, falsas centrais, falso motoboy, marketplaces, contas laranja, bets, cripto/P2P, maquininhas, consignado/INSS/FGTS e outros padrões brasileiros.

> **Aviso de independência:** este projeto não é afiliado, endossado ou mantido pela MITRE, pelo Center for Threat-Informed Defense ou pelo projeto Fight Fraud Framework. O projeto F3 foi usado apenas como referência arquitetural e metodológica.

## Conteúdo inicial

- 9 táticas brasileiras:
  - Preparação
  - Aproximação
  - Engenharia Social
  - Comprometimento de Conta/Dispositivo
  - Manipulação de Pagamento
  - Execução Financeira
  - Cash-out/Lavagem
  - Evasão/Encobrimento
  - Revitimização
- 30 técnicas brasileiras iniciais, incluindo:
  - Falso Comprovante de PIX
  - QR Code PIX Adulterado
  - Falso Boleto
  - Falsa Central Bancária
  - Falso Motoboy
  - WhatsApp Clonado ou Tomado
  - Falso Investimento
  - Golpe da Tarefa/Remuneração
  - Conta Laranja Alugada
  - Cash-out via Bet
  - Cash-out via Cripto/P2P
  - Fraude com Maquininha

## Estrutura da técnica

Cada técnica busca conter:

- ID
- nome em português
- nome global em inglês
- descrição
- tática(s)
- canais usados
- alvos comuns
- pré-requisitos
- sinais observáveis
- detecção
- mitigação
- evidências úteis
- relações com F3/MITRE ATT&CK

## Desenvolvimento local

```bash
npm install
npm run dev
```

Build de produção:

```bash
npm run build
```

## GitHub Pages

Este repositório está preparado para publicar via GitHub Pages usando GitHub Actions.

1. Crie o repositório `brazil-financial-fraud-framework` no GitHub.
2. Envie o código para a branch `main`.
3. Em `Settings → Pages → Build and deployment`, selecione `Source: GitHub Actions`.
4. A cada push na `main`, o workflow `.github/workflows/deploy.yml` fará o build e deploy.

URL esperada:

```text
https://debugactiveprocess.github.io/brazil-financial-fraud-framework/
```

Se o repositório tiver outro nome, ajuste o campo `base` em `vite.config.js`.

## Dados

Arquivos principais:

- `src/data/matrix-data.json` — dados usados pela aplicação.
- `public/br-fraud-v1.json` — export JSON público.
- `public/br-fraud-stix.json` — placeholder STIX inicial.
- `public/br-fraud-navigator.json` — placeholder Navigator Layer inicial.

O script `scripts/bootstrap_brazil_framework.py` recria a versão inicial dos dados brasileiros.

## Licença

Licenciado sob Apache License 2.0, salvo indicação em contrário. O código base foi adaptado de projeto open source de referência conforme a licença original.
