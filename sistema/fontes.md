# Fontes de dados

| Frente | Arquivo | ID | Acesso |
|---|---|---|---|
| Orçamento | [Controle_Contas](https://docs.google.com/spreadsheets/d/1iCyD4qZja2Qy8WZO57WtNIfpELBEmipv4OH7fZvxdMQ/edit) | `1iCyD4qZja2Qy8WZO57WtNIfpELBEmipv4OH7fZvxdMQ` | Somente leitura |
| Investimentos | [Investimentos](https://docs.google.com/spreadsheets/d/1fzQ7p6kzo2sZbMywn93TjHM0fHmyXfUk_1PNW_BgFuQ/edit) | `1fzQ7p6kzo2sZbMywn93TjHM0fHmyXfUk_1PNW_BgFuQ` | Somente leitura |
| Memória do sistema | [Hamdan_OS_Memoria](https://docs.google.com/spreadsheets/d/1H5s0abjd0kdII-4LKTSiCK0bksdeF9K8kUv5zbiqWjE/edit) | `1H5s0abjd0kdII-4LKTSiCK0bksdeF9K8kUv5zbiqWjE` | Leitura e escrita (aba Briefings) |
| Agenda e tarefas | Google Calendar `raphaelhamdan07@gmail.com` | — | Somente leitura |
| Notícias | Web + e-mails do Google News no Gmail | — | Leitura |

## Estrutura das planilhas

### Controle_Contas · aba `DataBase`
- Cabeçalho na linha 2: `Mês | Tipo Conta | Pilar | Descrição Conta | R$`. Dados a partir da linha 3.
- `Mês` é texto no formato `out.-26`. Há linhas antigas com `abr./26`: tratar `/` e `.-` como equivalentes.
- `Tipo Conta`: Fixa ou Variável. `Pilar`: Casa, Streaming, Educação, Transporte, Pets, Lazer, Estética, Saúde, Roupas, Outros.
- Valores em R$ com vírgula decimal. Há linhas sem valor (ignorar).
- Não há meta de orçamento por pilar (decisão de 17/10/2026).

### Controle_Contas · aba `Receitas`
- Cabeçalho na linha 4: `Fonte | Tipo | Valor | Início | Fim | Observação`. Dados a partir da linha 5.
- `Tipo`: Recorrente (vale de Início a Fim; Fim vazio = vigente) ou Extra (vale só no mês de Início).
- Mês no formato da DataBase (`out.-26`). `H5` = total recorrente vigente.
- Vigente desde out.-26: Receita Raphael R$ 9.000 e Receita Carinna R$ 6.000.

### Controle_Contas · aba `Vencimentos`
- Cabeçalho na linha 4: `Conta | Descrição na DataBase | Dia de vencimento | Dia do aviso | Valor fixo em € | Forma de pagamento | Ativa | Observação | Avisar N dias antes`. Dados a partir da linha 5. Coluna I tem prioridade sobre a D.
- Cadastradas em 17/10/2026: Internet (vence 4, aviso 30), Energia/Luz (vence 14, aviso 10), Academia (vence 5, aviso 30), Água (vence 2, aviso 30), Aluguel (vence 1, aviso 3 dias antes).

### Investimentos
- `Posição!A4:I14`: carteira consolidada (papel, classe, qtd, preço, valor, custo, proventos, P&L).
- `Alocação!A4:F9`: peso real vs. alvo por classe e status. `Alocação!A11:C22`: matemática da Rota B.
- `Parâmetros!A1:C27`: alvos, banda, aporte, macro (Selic, CDI, IPCA, IPCA+), datas de controle.
- `Acompanhamento!A4:I300`: ledger. Coluna I = Alerta (deve estar vazia).
- `Instruções!A1:B30`: rotina mensal do comitê e pendências abertas.

### Hamdan_OS_Memoria
- `Briefings!A1:K`: `Data | Formato | Síntese | Manchetes | Alertas | Patrimônio | Gasto do mês | Receita do mês | Poupança do mês | Compromissos | Enviado em`. Uma linha por dia, a partir da linha 2. Data em texto `AAAA-MM-DD`.
- Escrita só pela rotina das 7:00 (append). O dashboard lê a última linha.

### Google Calendar
- Tarefas do Google Tasks com data e horário aparecem como eventos do tipo FOCUS_TIME, com `tasks.google.com/task/` na descrição. O Calendar não mostra tarefas sem horário nem o status de concluída.
