# Como contribuir (guia rápido)

Este documento é uma referência prática para contribuir com a **Matriz Brasileira de Fraudes Financeiras**.

O projeto existe para a comunidade: quanto mais golpes e fraudes forem mapeados (com sinais observáveis, detecção e mitigação), **mais todo mundo ganha** — mais clareza, mais interoperabilidade e mais eficácia operacional.

> **Regra de ouro:** contribuições devem ser **defensivas** e **não** devem ensinar alguém a cometer fraudes.

## Formas de contribuir

Você pode contribuir de várias formas:

1. **Sugerir uma nova técnica** (Issue ou PR)
2. **Melhorar uma técnica existente** (descrição, sinais observáveis, detecção, mitigação)
3. **Adicionar relações/mapeamentos** (ex.: para F3/ATT&CK quando fizer sentido)
4. **Adicionar exemplos brasileiros** (descritos de forma segura, sem dados sensíveis)
5. **Melhorar taxonomia** (táticas/categorias, nomenclaturas)
6. **Melhorar o site** (UI/UX, navegação, busca, conteúdo)

## Critérios para incluir uma técnica

Uma técnica deve, idealmente:

- representar **comportamento observável** (algo que pode ser visto/monitorado/auditado);
- ter utilidade para **prevenção, detecção, resposta, investigação ou inteligência**;
- ser relevante para o **contexto brasileiro**;
- evitar especificidade excessiva de uma única instituição (prefira generalizar);
- incluir, quando possível, **sinais observáveis**, **detecção**, **mitigação** e **evidências úteis**.

## Modelo sugerido (copie e cole)

Use este template ao abrir uma Issue ou PR com nova técnica:

```text
ID sugerido: BRF-XXXX
Nome (PT-BR):
Nome global (EN):
Tática(s):

Descrição:

Canais usados:

Alvos comuns:

Pré-requisitos:

Sinais observáveis:
- 
- 

Detecção:
- 
- 

Mitigação:
- 
- 

Evidências úteis:
- 
- 

Relações/mapeamentos (opcional):
- F3:
- ATT&CK:

Exemplos brasileiros (sem dados sensíveis):
- 
```

## Onde editar os dados

Os dados usados pelo site ficam principalmente em:

- `src/data/matrix-data.json`

E existem exports públicos em:

- `public/br-fraud-v1.json`
- `public/br-fraud-stix.json`
- `public/br-fraud-navigator.json`

## Boas práticas de segurança

Não inclua:

- dados pessoais (PII), chaves PIX reais, números de conta/cartão, documentos, prints com dados sensíveis;
- segredos (tokens, credenciais, chaves de API);
- instruções operacionais detalhadas para execução de fraude.

Prefira descrever **padrões** e **sinais**.

## Como abrir um Pull Request

Fluxo sugerido:

1. Fork do repositório
2. Crie uma branch: `git checkout -b feat/nova-tecnica-brf-XXXX`
3. Commit: `git commit -m "data: add BRF-XXXX <nome>"`
4. Push e abra o PR

## Dúvidas / sugestões

Se tiver dúvida, abra uma Issue — mesmo que seja só para discutir o nome/escopo de uma técnica.
