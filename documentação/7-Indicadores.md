## 7. Indicadores de desempenho

_Apresente aqui os principais indicadores de desempenho e algumas metas para o processo. Atenção: as informações necessárias para gerar os indicadores devem estar contempladas no modelo relacional. Defina no mínimo 3 indicadores de desempenho._

_Usar o seguinte modelo:_

| **Indicador** | **Objetivos** | **Descrição** | **Fonte de dados** | **Fórmula de cálculo** |
| ---           | ---           | ---           | ---             | ---             |
| Tempo médio de permanência | Acompanhar quanto tempo as crianças ficam e a demanda do atendimento (Processo 1) | Média, em minutos, do tempo entre a entrada e a saída dos atendimentos finalizados | Tabela ATENDIMENTO (`hora_entrada`, `hora_saida`) | soma dos minutos de permanência / número de atendimentos finalizados |
| Taxa de atendimentos pagos | Controlar o que já foi cobrado e recebido na saída (Processo 1) | Percentual de atendimentos finalizados com pagamento confirmado | Tabela ATENDIMENTO (`pago`, `hora_saida`) | (atendimentos finalizados com `pago` verdadeiro / atendimentos finalizados) * 100 |
| Taxa de eventos confirmados | Medir quantos orçamentos de festa viram eventos confirmados (Processo 2) | Percentual de eventos com situação CONFIRMADO em relação a todos os eventos solicitados | Tabela EVENTO (`status`) | (eventos CONFIRMADO / total de eventos) * 100 |
| Valor médio contratado por evento | Entender o tamanho dos orçamentos e os serviços mais procurados (Processo 2) | Média do total de serviços contratados por evento (quantidade x valor praticado) | Tabelas CONTRATACAO (`quantidade`, `valor_servico`) e EVENTO | soma de (quantidade x valor_servico) / número de eventos com serviços contratados |
| Taxa de conclusão dos checklists | Verificar se a equipe confere o espaço antes e depois das festas (Processo 2) | Percentual de itens de checklist concluídos, por tipo (pré ou pós-evento) | Tabela CHECKLIST_EVENTO (`tipo`, `concluido`) | (itens concluídos / total de itens) * 100 |

_Obs.: todas as informações para gerar os indicadores devem estar no modelo relacional._

Todas as informações usadas estão no modelo relacional, como mostram as consultas abaixo (MySQL):

```sql
-- 1. Tempo médio de permanência (minutos)
SELECT ROUND(AVG(TIME_TO_SEC(TIMEDIFF(hora_saida, hora_entrada)) / 60), 1) AS tempo_medio_min
FROM ATENDIMENTO
WHERE hora_saida IS NOT NULL;

-- 2. Taxa de atendimentos pagos (%)
SELECT ROUND(100 * SUM(pago) / COUNT(*), 1) AS taxa_pagos_pct
FROM ATENDIMENTO
WHERE hora_saida IS NOT NULL;

-- 3. Taxa de eventos confirmados (%)
SELECT ROUND(100 * SUM(status = 'CONFIRMADO') / COUNT(*), 1) AS taxa_confirmados_pct
FROM EVENTO;

-- 4. Valor médio contratado por evento (R$)
SELECT ROUND(SUM(quantidade * valor_servico) / COUNT(DISTINCT cod_evento), 2) AS valor_medio_evento
FROM CONTRATACAO;

-- 5. Taxa de conclusão dos checklists (%), por tipo
SELECT tipo, ROUND(100 * SUM(concluido) / COUNT(*), 1) AS taxa_conclusao_pct
FROM CHECKLIST_EVENTO
GROUP BY tipo;
```

> ⚠️ **CONFERIR:** as consultas foram escritas a partir do dicionário de dados e **não foram executadas** no MySQL. Rode cada uma no Workbench com o banco preenchido e corrija se algum nome de coluna estiver diferente.
>
> ⚠️ **FALTA:** o template pede "algumas metas" para os indicadores. Os arquivos não trazem metas combinadas com a Brinquedoteca. Se o grupo tiver (por exemplo, "pelo menos X% dos atendimentos pagos na saída"), acrescente uma coluna **Meta** na tabela.

### 7.1. Gráficos dos Indicadores de desempenho

_Apresente aqui os gráficos dos indicadores de desempenho._

> ⚠️ **FALTA PRINT / GRÁFICO:** nenhum gráfico foi enviado. Para fazer: rodar as consultas acima no Workbench com o banco preenchido e montar um gráfico simples de cada indicador (barras ou pizza, em planilha ou na própria tela do sistema, se houver) e colocar as imagens aqui, por exemplo em `imagem/indicador-tempo-medio.png`.
