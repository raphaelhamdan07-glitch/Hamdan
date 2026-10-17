# Hamdan OS

Sistema pessoal de bolso. Todo dia às 7:00 (Lisboa), uma tarefa agendada do Claude lê as fontes, monta um briefing no formato Brevidade Inteligente e envia por e-mail, com notificação no celular.

## Frentes
| Frente | Fonte | O que o briefing traz |
|---|---|---|
| ✅ Estudos e tarefas | Planilha `Hamdan_OS_Rotina` | Lista do dia, sequências, prazos vencidos |
| 🌍 Notícias | Web + Google News | Geopolítica, economia, tecnologia, Brasil/Portugal, sem repetir |
| 💰 Orçamento | Planilha `Controle_Contas` | Mês vs. média de 3 meses, top gastos, alertas |
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

## Seu uso diário
1. Abra o e-mail das 7:00. A síntese no topo resume o dia.
2. Ao concluir uma tarefa, marque **Feito?** na planilha Rotina (funciona no app do Sheets no celular).
3. Tarefa nova: adicione uma linha na aba Tarefas.

## Arquivos
- `sistema/ROTINA_DIARIA.md`: o roteiro que a tarefa das 7:00 executa.
- `sistema/brevidade.md`: regras de escrita.
- `sistema/investimentos.md`: mandato e limites do que o briefing pode recomendar.
- `sistema/fontes.md`: IDs e estrutura das planilhas.
- `templates/email.html`: modelo do e-mail.
- `briefings/`: histórico, um arquivo por dia.
