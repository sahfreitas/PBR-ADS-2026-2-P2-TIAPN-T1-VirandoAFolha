# Banco de dados

Scripts SQL do **Virando a Folha**, o sistema da Brinquedoteca Barreiro. O banco é o **MySQL 8.0** e se chama `brinquedoteca`.

Os scripts ficam em [`database/`](database/) e devem ser executados **nesta ordem**, no MySQL Workbench:

| Ordem | Arquivo | O que faz |
|:---:|---|---|
| 1 | [`schema.sql`](database/schema.sql) | Cria o banco, as tabelas e os triggers |
| 2 | [`seed.sql`](database/seed.sql) | Insere dados fictícios para teste |
| 3 | [`consultas.sql`](database/consultas.sql) | Consultas SQL de exemplo (executar uma por vez) |

> Para rodar cada arquivo no Workbench, abra-o (File → Open SQL Script) e execute o script inteiro com o raio ⚡ (Ctrl+Shift+Enter). No `consultas.sql`, selecione o bloco de uma consulta e use Ctrl+Enter.

## schema.sql

Cria o banco do zero, a partir do Projeto Lógico.

> **Atenção:** o script começa com `DROP DATABASE IF EXISTS brinquedoteca`. Ele **apaga e recria** o banco, então tudo o que existir nele é perdido.

**Tabelas (18)**

| Grupo | Tabelas |
|---|---|
| Pessoas | `PESSOA`, `TELEFONE_PESSOA`, `RESPONSAVEL`, `FUNCIONARIO`, `RECEPCIONISTA`, `MONITOR` |
| Crianças | `CRIANCA`, `RESPONSAVEL_ADICIONAL` |
| Atendimentos | `ATENDIMENTO`, `ACOMPANHA` |
| Eventos | `EVENTO`, `FICHA_BRIEFING`, `SERVICO`, `PARTICIPACAO`, `CONTRATACAO`, `CHECKLIST_EVENTO` |
| Sistema | `CONFIGURACAO`, `ACESSO` |

* `PESSOA` é a superclasse de `RESPONSAVEL` e `FUNCIONARIO`; `RECEPCIONISTA` e `MONITOR` são especializações de `FUNCIONARIO`.
* `CRIANCA` é entidade fraca de `RESPONSAVEL`: a chave é composta pelo responsável e por um número sequencial.
* `ACESSO` guarda o login do sistema: CPF, senha em **hash** (nunca a senha pura) e perfil (`ADMIN`, `FUNCIONARIO` ou `RESPONSAVEL`).
* `CONFIGURACAO` e `CHECKLIST_EVENTO` foram acrescentadas depois do Projeto Lógico, a partir do BPMN TO-BE.

**Triggers (regras que o `CHECK` do MySQL não consegue fazer)**

* A data de nascimento não pode estar no futuro (pessoa e criança).
* Uma pessoa não pode ser responsável e funcionário ao mesmo tempo.
* A criança é numerada automaticamente (1, 2, 3...) dentro de cada responsável.
* O responsável adicional deve ser outra pessoa que não o principal, e cada criança tem no máximo um adicional.
* A data do atendimento não pode ser futura.

## seed.sql

Popula o banco com **dados fictícios**, para testar o sistema e tirar prints. Rode somente depois do `schema.sql`.

Inclui 5 responsáveis, 5 funcionários (com recepcionistas e monitores), crianças, responsáveis adicionais, atendimentos, serviços, eventos com briefing, equipe e contratações, checklists, a configuração do sistema e os acessos dos funcionários.

Os acessos de teste ficam no final do arquivo, na seção `ACESSO`, junto com a senha de teste. Os CPFs, nomes e telefones do seed são inventados.

## consultas.sql

Contém as **10 consultas** da Atividade 3 de Banco de Dados, cada uma com o enunciado no comentário acima dela. Execute uma por vez para tirar o print do resultado.

| Nº | Recurso de SQL | O que a consulta responde |
|:---:|---|---|
| 1 | `DISTINCT`, `BETWEEN`, `ORDER BY` e 2 `JOIN` | Serviços contratados em eventos de dezembro de 2026, sem repetição |
| 2 | `LEFT JOIN` | Todos os eventos e seus serviços, inclusive eventos sem serviço contratado |
| 3 | `RIGHT JOIN` | Todos os serviços do catálogo e os eventos que os contrataram, inclusive serviços nunca contratados |
| 4 | `IS NULL` e `JOIN` | Atendimentos em andamento (sem hora de saída) e a criança atendida |
| 5 | `AND` e `OR` com 2 `JOIN` | Eventos confirmados ou em orçamento com mais de 20 convidados, e o responsável |
| 6 | `LIKE` | Crianças cujo nome contém "Lima" |
| 7 | `GROUP BY` e `SUM` | Valor total contratado em cada evento |
| 8 | `HAVING` e 2 `JOIN` | Responsáveis com mais de uma criança cadastrada |
| 9a | Subconsulta sem correlação | Serviços com valor acima da média do catálogo |
| 9b | Subconsulta correlacionada e `JOIN` | Quantidade de eventos de cada funcionário na equipe |

## Conexão com o sistema

O back-end (Node.js) se conecta a este banco pelo arquivo `db.js`, usando as variáveis do `.env` (`DB_HOST`, `DB_PORT`, `DB_USER`, `DB_PASSWORD` e `DB_NAME`). O `DB_NAME` precisa ser `brinquedoteca`. As instruções completas de execução estão no [README do código-fonte](../README.md).