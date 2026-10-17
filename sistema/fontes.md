# Fontes de dados

| Frente | Arquivo | ID | Acesso |
|---|---|---|---|
| Orçamento | [Controle_Contas](https://docs.google.com/spreadsheets/d/1iCyD4qZja2Qy8WZO57WtNIfpELBEmipv4OH7fZvxdMQ/edit) | `1iCyD4qZja2Qy8WZO57WtNIfpELBEmipv4OH7fZvxdMQ` | Somente leitura |
| Investimentos | [Investimentos](https://docs.google.com/spreadsheets/d/1fzQ7p6kzo2sZbMywn93TjHM0fHmyXfUk_1PNW_BgFuQ/edit) | `1fzQ7p6kzo2sZbMywn93TjHM0fHmyXfUk_1PNW_BgFuQ` | Somente leitura |
| Estudos e tarefas | [Hamdan_OS_Rotina](https://docs.google.com/spreadsheets/d/1H5s0abjd0kdII-4LKTSiCK0bksdeF9K8kUv5zbiqWjE/edit) | `1H5s0abjd0kdII-4LKTSiCK0bksdeF9K8kUv5zbiqWjE` | Leitura e escrita (abas Tarefas e Log) |
| Notícias | Web + e-mails do Google News no Gmail | — | Leitura |

## Estrutura das planilhas

### Controle_Contas · aba `DataBase`
- Cabeçalho na linha 2: `Mês | Tipo Conta | Pilar | Descrição Conta | R$`. Dados a partir da linha 3.
- `Mês` é texto no formato `out.-26`. Há linhas antigas com `abr./26`: tratar `/` e `.-` como equivalentes.
- `Tipo Conta`: Fixa ou Variável. `Pilar`: Casa, Streaming, Educação, Transporte, Pets, Lazer, Estética, Saúde, Roupas, Outros.
- Valores em R$ com vírgula decimal. Há linhas sem valor (ignorar).
- A planilha só tem despesas. Não há receita nem meta de orçamento.

### Investimentos
- `Posição!A4:I14`: carteira consolidada (papel, classe, qtd, preço, valor, custo, proventos, P&L).
- `Alocação!A4:F9`: peso real vs. alvo por classe e status. `Alocação!A11:C22`: matemática da Rota B.
- `Parâmetros!A1:C27`: alvos, banda, aporte, macro (Selic, CDI, IPCA, IPCA+), datas de controle.
- `Acompanhamento!A4:I300`: ledger. Coluna I = Alerta (deve estar vazia).
- `Instruções!A1:B30`: rotina mensal do comitê e pendências abertas.

### Hamdan_OS_Rotina
- `Tarefas!A4:L`: `ID | Tarefa | Frente | Frequência | Dias da semana | Prazo | Prioridade | Status | Feito? | Última conclusão | Sequência (dias) | Observação`. Dados a partir da linha 5.
- `Log!A1:E`: `Data | ID | Tarefa | Frente | Registrado por`.
