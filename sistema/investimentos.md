# Investimentos · Como o briefing diário usa o comitê

O sistema completo de decisão é o **Comitê de Investimentos** em `sistema/comite_investimentos.md` (Agentes A1 a A4). Ele roda uma vez por mês, numa sessão interativa, porque o Agente 2 precisa perguntar o aporte disponível. O briefing diário **não roda o comitê**.

## O que o briefing diário aplica do comitê
1. **Regras de integridade (seção 0.1), sempre:**
   - Todo número da carteira ou macro vem com fonte e data. Números da planilha citam a aba e a data dos preços (`Parâmetros!B26`).
   - Sem dado, escreva `N/D`. Nunca estime por memória.
   - Fontes divergentes: mostre as duas e use a mais conservadora.
2. **Agente 1, versão resumida:** patrimônio, peso por classe, distorção vs. alvo e higiene do arquivo (seção 3.2e). Status pela régua do comitê: `SOBREALOCADO` (> +5 pp), `NA BANDA`, `SUBALOCADO` (< −5 pp), `CRÍTICO` (< −15 pp).
3. **Plano do mês:** mostra a aritmética da aba Alocação (Rota B, tranche, rateio), sempre como "aritmética da planilha, pendente do comitê".

## O que o briefing diário não pode fazer
- Recomendar ativo, preço de entrada ou venda. Isso é do Agente 3, com veto, e do selo do Agente 4.
- Calcular PI, margem de segurança ou Graham.
- Escrever na planilha Investimentos.

## Lembrete do comitê
- Do dia 1 ao dia 5 de cada mês, ou quando a última revisão (`Parâmetros!B27`) tiver 25 dias ou mais, o briefing abre a seção Carteira com: "Comitê de <mês> pendente." e o checklist da seção 8 do comitê, já com o que o sistema sabe preenchido (mês de referência, pesos-alvo da planilha, data dos preços). O aporte disponível fica em branco, para o Agente 2 perguntar.
- Para rodar o comitê: abra uma sessão e peça "rodar o comitê de <mês>". A sessão lê `sistema/comite_investimentos.md` e segue A1 → A4.

## Ajustes entre o comitê e a planilha
- **Referência de custo de oportunidade (decidido em 17/10/2026):** vale o Tesouro **IPCA+ 2032**, o título que a carteira tem e que a planilha usa (`Parâmetros`, "Piso de DY — ações"). Onde o comitê diz IPCA+ 2035 (critério 5 do Graham, seção 4.1 e Entrega A2), leia IPCA+ 2032.
- **Régua de status:** a aba Alocação marca "CRITICO" e "Subalocado" com limites próprios; o comitê define `CRÍTICO` como < −15 pp. O briefing usa a régua do comitê.

## Histórico de correções
- 17/10/2026: `Posição!D12:D13` (saldo das caixinhas) usava `LOOKUP(2;1/(...))`, que não funciona no Google Sheets sem ARRAYFORMULA e devolvia 0. Trocado por `INDEX(SORT(FILTER(...)))`.
  - O erro só aparecia desde 09/10, quando os lançamentos do tipo Saldo substituíram a estimativa por CDI. O comitê de 01/10 trabalhou com as caixinhas estimadas (Histórico: patrimônio de R$ 48.333, Renda Fixa em R$ 42.417), então a decisão de outubro não foi afetada.
  - Afetados: a aba Alocação entre 09/10 e 17/10 (mostrava patrimônio de R$ 9.901 e Renda Fixa em 14,6%) e o primeiro briefing (17/10), que atribuiu o erro ao comitê de outubro por engano.
