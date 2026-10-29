# Central Agro Dados

Repositório de dados publicados pelo SONYC para consumo do Central Agro.

> Este repositório **não deve ser conectado ao Vercel para deploy automático**. O Vercel apenas consome os JSON publicados aqui.

## Fluxo

```text
BM / planilha local
→ SONYC
→ GitHub
→ Vercel / Central Agro
```

## Arquivos produtivos

- `data-live/produtos.json` — produtos, preços, custos, estoque, reservas e saldo.
- `data-live/sales-operational.json` — vendas operacionais do mês corrente.
- `data-live/ticket.json` — ticket médio mensal e diagnóstico.
- `data-live/analyses.json` — base consolidada das análises especiais.
- `data-live/racao.json` — ração a granel, derivado de `analyses.json`.
- `data-live/milho.json` — sementes/milho, derivado de `analyses.json`.
- `data-live/vacinas.json` — vacinas, derivado de `analyses.json`.
- `data-live/status.json` — estado e totais do último ciclo.
- `data-live/logs.json` — histórico dos últimos ciclos.
- `data-live/indicadores.json` — histórico financeiro e formas de pagamento da planilha Indicadores.

## Regras

- `status.json` deve refletir o mesmo ciclo dos arquivos operacionais.
- `ticket.json` usa o mês corrente e despreza documentos cancelados.
- `racao.json`, `milho.json` e `vacinas.json` são derivados de `analyses.json`.
- `indicadores.json` preserva os valores da planilha; divergências históricas devem ser corrigidas na origem.
- Arquivos de teste não devem permanecer em `data-live`.
- O SONYC 3.2.7 usa `cycle_id` comum para identificar os arquivos de um mesmo ciclo.
