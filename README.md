# Hamdan OS

Sistema pessoal de bolso. Todo dia às 7:00 (Lisboa), uma tarefa agendada do Claude lê as fontes, monta um briefing no formato Brevidade Inteligente e envia por e-mail, com notificação no celular.

## Frentes
| Frente | Fonte | O que o briefing traz |
|---|---|---|
| ✅ Agenda e tarefas | Google Calendar + planilha `Hamdan_OS_Rotina` | Compromissos e Google Tasks do dia, estudos recorrentes, sequências |
| 🌍 Notícias | Web + Google News | Geopolítica, economia, tecnologia, Brasil/Portugal, sem repetir |
| 💰 Orçamento | Planilha `Controle_Contas` (DataBase + Receitas) | Gasto vs. média de 3 meses, taxa de poupança, alertas |
| 📈 Investimentos | Planilha `Investimentos` | Patrimônio, alocação vs. alvo, plano do mês, higiene |

## Como funciona
```
07:00 Lisboa ── tarefa agendada (sessão nova) ──► lê sistema/ROTINA_DIARIA.md
     │
     ├─ Rotina: registra conclusões de ontem no Log, zera caixas, monta a lista de hoje
     ├─ Notícias: pesquisa 24h, compara com os 3 últimos briefings, descarta repetidas
     ├─ Orçamento e Carteira: leitura das planilhas (sem escrever nelas)
     │
     ├─► briefings/AAAA-MM-DD.md (memória para o dia seguinte, commit no repositório)
     └─► Gmail (HTML) + push no celular
```

## Dashboard
[Hamdan OS no claude.ai](https://claude.ai/artifact/T8312Sfqrh1ysgJevGr3zx). Lê ao vivo as planilhas e o Google Calendar com a sua conta toda vez que você abre: carteira, alocação vs. alvo, plano do mês, gastos e poupança por mês, gastos por pilar, agenda dos próximos 7 dias e rotina.

## Comitê mensal
Roda numa sessão interativa: peça "rodar o comitê de <mês>". Segue `sistema/comite_investimentos.md` (Agentes A1 a A4). O briefing diário só lembra e mostra a aritmética da planilha.

## Seu uso diário
1. Abra o e-mail das 7:00. A síntese no topo resume o dia.
2. Ao concluir uma tarefa, marque **Feito?** na planilha Rotina (funciona no app do Sheets no celular).
3. Tarefa nova: adicione uma linha na aba Tarefas.

## Arquivos
- `sistema/ROTINA_DIARIA.md`: o roteiro que a tarefa das 7:00 executa.
- `sistema/brevidade.md`: regras de escrita.
- `sistema/investimentos.md`: o que o briefing aplica do comitê e o que não pode fazer.
- `sistema/comite_investimentos.md`: o comitê mensal (A1 a A4), como você escreveu.
- `sistema/fontes.md`: IDs e estrutura das planilhas.
- `templates/email.html`: modelo do e-mail.
- `briefings/`: histórico, um arquivo por dia.
