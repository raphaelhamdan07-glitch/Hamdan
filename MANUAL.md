# Hamdan OS · Manual de uso

## Ciclo do dia
| Quando | O que acontece | Onde você vê |
|---|---|---|
| 06:50 (Lisboa) | A tarefa agendada abre uma sessão nova, lê agenda, notícias, orçamento e carteira, grava a memória e envia o e-mail | — |
| ~07:00 | Chega o briefing no Gmail e a notificação no celular | Gmail · celular |
| Qualquer hora | O dashboard lê as planilhas e o Calendar no momento em que você abre | claude.ai (artefato Hamdan OS) |

- Segunda a sexta: briefing completo. Sábado e domingo: briefing curto (agenda e 1 notícia por frente).
- Do dia 1 ao 5 de cada mês, o briefing lembra o comitê de investimentos.
- No dia do aviso de cada conta, o e-mail abre com "💳 Contas a pagar" e a notificação do celular diz o que transferir.

## O que você alimenta (e só isso)
| Frequência | Onde | O quê |
|---|---|---|
| Contínuo | Google Calendar / Google Tasks | Compromissos e tarefas, como já faz. Tarefa do Google Tasks só aparece se tiver data e **horário**. |
| Mensal | Controle_Contas · DataBase | Despesas do mês. Mês sempre no formato `nov.-26` (minúsculo, ponto, hífen). |
| Quando mudar | Controle_Contas · Vencimentos | Conta nova, dia de vencimento ou de aviso, valor fixo em €, forma de pagamento. Ativa = Não para desligar o aviso. |
| Quando mudar | Controle_Contas · Receitas | Salário novo: ponha Fim no mês anterior da linha antiga e crie uma linha nova. Bônus ou extra: linha Tipo = Extra. |
| Mensal | Investimentos | A rotina da aba Instruções: movimentações, Saldo das caixinhas, preços, PU do Tesouro, macro, Histórico. |
| Mensal | Sessão no Claude | "Rodar o comitê de <mês>" com o aporte disponível. |

Tudo o mais é automático: notícias, agenda, cálculos, alertas, memória e dashboard.

## O que o dashboard mostra e de onde vem
| Bloco | Fonte | Atualiza quando |
|---|---|---|
| Contas a pagar | Controle_Contas · Vencimentos + DataBase | Ao abrir; fica vermelho do dia do aviso até o vencimento |
| Topo (patrimônio, Renda Fixa, gastos, poupança) | Investimentos + Controle_Contas | Ao abrir, com o que estiver nas planilhas |
| Agenda dos próximos 7 dias | Google Calendar | Ao abrir |
| Briefing de hoje | Hamdan_OS_Memoria | Depois que a rotina das 7:00 roda |
| Carteira (alocação, histórico, plano, posição) | Investimentos | Ao abrir; os preços são os digitados no comitê |
| Orçamento (12 meses, pilares) | Controle_Contas | Ao abrir |

Os preços da carteira **não** são de mercado em tempo real: o patrimônio muda quando você atualiza a planilha no comitê.

## Sinais de problema e o que fazer
| Sinal | Causa provável | O que fazer |
|---|---|---|
| Nenhum e-mail até 07:15 | A tarefa falhou ou não rodou | Abra a sessão mais recente da tarefa "Briefing diário 7h" no claude.ai/code e leia a última linha |
| Notificação começando com "FALHA:" | Um conector caiu ou pediu nova autorização | Reconecte em claude.ai/customize/connectors |
| Card "Briefing de hoje" com data antiga | A rotina não gravou a memória hoje | Mesmo caso do e-mail |
| Um card do dashboard com "Failed to load" | Permissão do conector no dashboard ou planilha renomeada/movida | Abra Sources no dashboard; não renomeie as abas das planilhas |
| Mês novo não aparece no orçamento | Mês digitado em outro formato | Corrija para `nov.-26` |
| Notícias repetidas | Memória não foi lida | Verifique se a aba Briefings da Hamdan_OS_Memoria está intacta |

## Não faça
- Não renomeie as planilhas, as abas nem mude a ordem das colunas: o sistema lê por posição.
- Não edite a aba Briefings da Hamdan_OS_Memoria.
- Não apague a tarefa "Briefing diário 7h"; para pausar, desative-a.
