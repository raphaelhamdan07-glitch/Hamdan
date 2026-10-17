# Hamdan OS

Sistema pessoal de bolso. Todo dia às 7:00 (Lisboa), uma tarefa agendada do Claude lê as fontes, monta um briefing no formato Brevidade Inteligente e envia por e-mail, com notificação no celular.

## Frentes
| Frente | Fonte | O que o briefing traz |
|---|---|---|
| 💳 Contas a pagar | Planilha `Controle_Contas` (Vencimentos) | Aviso antes do vencimento de aluguel, internet, energia, água e academia |
| ✅ Agenda e tarefas | Google Calendar | Compromissos e Google Tasks do dia |
| 🌍 Notícias | Web + Google News | Geopolítica, economia, tecnologia, Brasil/Portugal, sem repetir |
| 💰 Orçamento | Planilha `Controle_Contas` (DataBase + Receitas) | Gasto vs. média de 3 meses, taxa de poupança, alertas |
| 📈 Investimentos | Planilha `Investimentos` | Patrimônio, alocação vs. alvo, plano do mês, higiene |

## Como funciona
```
07:00 Lisboa ── tarefa agendada (sessão nova) ──► lê sistema/ROTINA_DIARIA.md
     │
     ├─ Contas: o que vence nos próximos dias (aba Vencimentos)
     ├─ Agenda: compromissos e tarefas do dia no Google Calendar
     ├─ Notícias: pesquisa 24h, compara com os 3 últimos briefings, descarta repetidas
     ├─ Orçamento e Carteira: leitura das planilhas (sem escrever nelas)
     │
     ├─► Hamdan_OS_Memoria (planilha: memória para o dia seguinte e para o dashboard)
     ├─► briefings/AAAA-MM-DD.md (cópia no repositório, se o push funcionar)
     └─► Gmail (HTML) + push no celular
```

## Dashboard
[Hamdan OS no claude.ai](https://claude.ai/artifact/T8312Sfqrh1ysgJevGr3zx). Lê ao vivo as planilhas e o Google Calendar com a sua conta toda vez que você abre: contas a pagar, carteira, alocação vs. alvo, plano do mês, gastos e poupança por mês, gastos por pilar, agenda dos próximos 7 dias e o último briefing.

## Comitê mensal
Roda numa sessão interativa: peça "rodar o comitê de <mês>". Segue `sistema/comite_investimentos.md` (Agentes A1 a A4). O briefing diário só lembra e mostra a aritmética da planilha.

## Seu uso diário
1. Abra o e-mail das 7:00. A síntese no topo resume o dia.
2. Tarefas e compromissos: continue usando o Google Calendar e o Google Tasks (com horário).
3. Mensal: lançar despesas na Controle_Contas, movimentações na Investimentos e rodar o comitê.

## Arquivos
- `sistema/ROTINA_DIARIA.md`: o roteiro que a tarefa das 7:00 executa.
- `sistema/brevidade.md`: regras de escrita.
- `sistema/investimentos.md`: o que o briefing aplica do comitê e o que não pode fazer.
- `sistema/comite_investimentos.md`: o comitê mensal (A1 a A4), como você escreveu.
- `sistema/fontes.md`: IDs e estrutura das planilhas.
- `templates/email.html`: modelo do e-mail.
- `briefings/`: histórico, um arquivo por dia.
