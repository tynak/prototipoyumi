# Escolher data de vencimento para renegociação de parcela única

> **Card:** CNT-3010 · Squad Pagadoria · Type: Task · Epic: Validar
> **Notion:** https://app.notion.com/p/38f0ef8b9898804dbb1cdca82af21186

## Contexto / Origem
No fluxo de "Renegociar Parcela", quando a renegociação é dividida em 2+ parcelas, o usuário já consegue definir a data de vencimento de cada nova parcela (etapa "Parcelas"). Quando resulta em **uma única parcela**, esse campo não aparece e o vencimento é fixado automaticamente em D+1 (dia seguinte).

## Problema
Hoje, ao renegociar em parcela única, o usuário não tem controle sobre a data de vencimento — o sistema força D+1. Isso impede acordos em que o cliente combina pagar a parcela única numa data específica (ex.: data do salário), gerando atrito e retrabalho para ajustar manualmente.

## Objetivo
Permitir que o usuário escolha a data de vencimento também quando a renegociação resulta em parcela única, mantendo paridade com o fluxo de múltiplas parcelas.

## Escopo (P0)
- Na etapa "Parcelas", quando a quantidade for **1**, exibir o campo "Data de vencimento" editável para a parcela única.
- Valor padrão sugerido do campo: D+1 (comportamento atual), porém editável.
- A data escolhida deve ser propagada para as etapas seguintes (Rateio/Revisão) e persistida na geração da cobrança.

## Fora de escopo
- Mudança nas regras de vencimento do fluxo com múltiplas parcelas — já funciona e não é alvo desta entrega.
- Alteração de data de vencimento de parcelas já geradas/pagas (fluxo separado).

## User stories
- Como operador da renegociação, quero escolher a data de vencimento quando o acordo for em parcela única, para refletir a data combinada com o cliente.

## Critérios de aceite
- [ ] Com quantidade de parcelas = 1, o campo "Data de vencimento" aparece e é editável.
- [ ] O padrão exibido é D+1, mas pode ser alterado.
- [ ] A data selecionada aparece corretamente na Revisão e na cobrança gerada.
- [ ] Validação de data mínima permitida — A definir no refinamento (pode ser hoje? só futuro?).

## Dependências e riscos
- Validar com QITech/gateway se há restrição de data mínima/máxima de vencimento na geração da cobrança.

## Perguntas em aberto
- [ ] Qual a data mínima permitida (hoje, D+1, ou outra)? — Thais/refinamento
- [ ] Há data máxima de vencimento permitida? — Thais/refinamento
