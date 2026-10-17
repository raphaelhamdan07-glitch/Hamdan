# Investimentos · Regras do mandato

> **Pendente:** colar aqui as instruções e skills do sistema de investimentos que está no Claude Projects (filtro fundamentalista, vetos, comitê). Enquanto isso, valem as regras abaixo, extraídas da própria planilha `Investimentos`.

## Mandato (aba Parâmetros)
- Alocação-alvo: Renda Fixa 40% · FIIs 25% · Ações Brasil 15% · Exterior 20%.
- Banda de tolerância: ±5 pp. Classe fora da banda exige ação no mês.
- Aporte mensal: R$ 500. Ticket mínimo por classe: R$ 200 (abaixo disso, vai para a fila de aportes).
- Rota B: migrar o excesso de Renda Fixa em 12 tranches mensais a partir da Caixinha Nubank 100% CDI (2 já executadas: set/26 e out/26).

## Filtro (feito no comitê, não na planilha)
- Piso de DY de ações: 2/3 da taxa real do Tesouro IPCA+ de referência.
- Piso de DY de FIIs (equivalente bruto): Selic × 0,80.
- Graham, margem de segurança e vetos continuam no comitê mensal.

## O que o briefing diário pode dizer
- Informar posição, distorções, plano aritmético do mês (aba Alocação) e alertas de higiene.
- Lembrar o comitê quando a última revisão tiver 25 dias ou mais.
- **Não pode** recomendar ativo específico, preço de entrada ou venda. Isso é do comitê mensal.

## Histórico de correções
- 17/10/2026: `Posição!D12:D13` (saldo das caixinhas) usava `LOOKUP(2;1/(...))`, que não funciona no Google Sheets sem ARRAYFORMULA e devolvia 0. Trocado por `INDEX(SORT(FILTER(...)))`. O patrimônio passou de R$ 9.901 para R$ 47.948 e a Renda Fixa de 14,6% para 82,4% da carteira. O rateio do comitê de out/26 foi calculado sobre o número errado.
