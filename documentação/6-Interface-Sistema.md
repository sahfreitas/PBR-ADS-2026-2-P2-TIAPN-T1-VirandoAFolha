# 6. Interface do Sistema

<span style="color:red">Pré-requisitos: <a href="../README.md#pré-requisitos"> README do projeto</a></span>

O sistema tem acesso separado para a equipe e para os responsáveis. A tela de login pede CPF e senha, e o menu lateral muda conforme o perfil. Os prints abaixo vêm das evidências da Atividade 4 e foram feitos com os usuários de teste da tabela a seguir.

| Perfil | Usuário de teste | CPF de login | O que enxerga |
| --- | --- | --- | --- |
| Coordenação | Beatriz, coordenadora | 222.333.444-01 | Todos os módulos, inclusive Funcionários e edição de Serviços |
| Recepção | João, recepcionista | 222.333.444-02 | Início, Atendimentos, Cadastro, Clientes, Eventos e Serviços |
| Monitoria | Camila (monitora) e Rafael (monitor) | 222.333.444-03 e 222.333.444-04 | Mesmas áreas da equipe, com escala de festas e checklists; Serviços somente leitura |
| Responsável | Júlia, Felipe, entre outros | 101.010.101-01, 999.999.999-99 | Meus dados e crianças, Meus eventos e Solicitar evento |

## 6.1. Tela principal do sistema

Depois do login, cada perfil cai em um painel inicial. A coordenação vê atalhos (registrar entrada, calcular valor, novo cadastro e novo evento), indicadores do dia (crianças na brinquedoteca, valor a receber, eventos confirmados e orçamentos em aberto), a escala de festas, as crianças brincando agora com valor parcial e os próximos eventos.

![Início da coordenação](imagem/telas/fig17.jpg "Figura 17. Início da coordenação (Beatriz)")

![Início da recepção](imagem/telas/fig18.jpg "Figura 18. Início da recepção (João): mesmo painel, sem a escala de festas")

![Início da monitora com Minha escala](imagem/telas/fig19.jpg "Figura 19. Início da monitora (Camila) com Minha escala")

![Início do monitor com Minha escala](imagem/telas/fig20.jpg "Figura 20. Início do monitor (Rafael): função na festa, horário de chegada e itens pendentes")

### Acesso ao sistema

![Tela de login](imagem/telas/fig01.jpg "Figura 1. Tela de login: CPF e senha, atalho para criar conta")

![Criar conta de responsável](imagem/telas/fig02.jpg "Figura 2. Criar conta de responsável (formulário vazio)")

![Login com senha incorreta](imagem/telas/fig03.jpg "Figura 3. Login com senha incorreta: o sistema recusa o acesso e avisa")

![Validação de senhas diferentes](imagem/telas/fig04.jpg "Figura 4. Validação: senha e confirmação diferentes")

![Validação de CPF já cadastrado](imagem/telas/fig05.jpg "Figura 5. Validação: CPF já pertence a um responsável")

## 6.2. Telas do processo 1

**Atendimento, permanência e saída da criança.** Atividade 1, *Identificar/cadastrar criança*: a equipe cadastra o responsável e as crianças na mesma tela e consulta a lista de famílias.

![Novo cadastro (vazio)](imagem/telas/fig27.jpg "Figura 27. Novo cadastro: responsável e crianças na mesma tela")

![Editar cadastro de uma família](imagem/telas/fig28.jpg "Figura 28. Editar cadastro: responsável com duas crianças, uma com segundo responsável e observação de alergia")

![Lista de clientes](imagem/telas/fig29.jpg "Figura 29. Lista de clientes (famílias), com acesso à edição")

Atividade 2, *Registrar horário de entrada*: a recepção escolhe a criança, a recepcionista e os monitores. O horário é marcado automaticamente.

![Registrar entrada](imagem/telas/fig21.jpg "Figura 21. Registrar entrada")

![Entrada preenchida](imagem/telas/fig22.jpg "Figura 22. Entrada preenchida, pronta para confirmar")

![Crianças brincando agora](imagem/telas/fig23.jpg "Figura 23. Crianças brincando agora: horário de entrada, tempo decorrido e valor parcial")

Atividades de saída, *Registrar horário de saída*, *Calcular e informar valor* e *Confirmar pagamento*: o sistema calcula o valor por minuto e mostra a permanência, a faixa e o valor da hora. A recepção confirma o pagamento ou deixa pendente.

![Saída registrada e valor a cobrar](imagem/telas/fig24.jpg "Figura 24. Saída registrada e valor a cobrar")

![Histórico de atendimentos](imagem/telas/fig25.jpg "Figura 25. Histórico de atendimentos finalizados")

![Calculadora de valor e tabela de preços](imagem/telas/fig26.jpg "Figura 26. Calculadora de valor, tabela rápida e tabela de preços por faixa; desconto de 5% para irmãos")

## 6.3. Telas do processo 2

**Solicitação, contratação e realização de festas e eventos.** Atividade 1, *Solicitar orçamento*: o responsável pede o evento pelo sistema, em passos (dados da festa e briefing).

![Meus eventos sem eventos](imagem/telas/fig11.jpg "Figura 11. Meus eventos (estado vazio)")

![Solicitar evento, passo 1 vazio](imagem/telas/fig12.jpg "Figura 12. Solicitar evento, passo 1: dados da festa (vazio)")

![Solicitar evento, passo 1 preenchido](imagem/telas/fig13.jpg "Figura 13. Solicitar evento, passo 1: dados preenchidos")

![Solicitar evento, passo 2](imagem/telas/fig14.jpg "Figura 14. Solicitar evento, passo 2: briefing")

![Início do responsável com evento em análise](imagem/telas/fig15.jpg "Figura 15. Início do responsável: o pedido fica em análise até a equipe retornar")

O passo 3 da solicitação (serviços) é praticamente igual ao passo 3 da tela da equipe, mostrado na Figura 35.

Atividade 2, *Registrar informações do evento, elaborar orçamento e confirmar reserva*: a equipe vê todos os eventos, filtra por situação e monta o evento em quatro passos.

![Lista de eventos](imagem/telas/fig30.jpg "Figura 30. Lista de eventos (todos), com data, responsável e situação")

![Filtro de eventos confirmados](imagem/telas/fig31.jpg "Figura 31. Filtro: eventos confirmados")

![Filtro de eventos cancelados](imagem/telas/fig32.jpg "Figura 32. Filtro: eventos cancelados")

![Evento passo 1](imagem/telas/fig33.jpg "Figura 33. Evento, passo 1: dados da festa")

![Evento passo 2](imagem/telas/fig34.jpg "Figura 34. Evento, passo 2: briefing")

![Evento passo 3](imagem/telas/fig35.jpg "Figura 35. Evento, passo 3: serviços e total do orçamento")

![Evento passo 4 vazio](imagem/telas/fig36.jpg "Figura 36. Evento, passo 4: equipe (vazia)")

![Equipe escalada](imagem/telas/fig37.jpg "Figura 37. Equipe escalada: pessoa, função na festa e horário de chegada")

![Confirmação do evento](imagem/telas/fig38.jpg "Figura 38. Confirmação antes de transformar o orçamento em evento confirmado")

![Evento confirmado com checklists](imagem/telas/fig39.jpg "Figura 39. Evento confirmado com checklists de antes e depois da festa")

![Lista de confirmados](imagem/telas/fig40.jpg "Figura 40. O evento passa a aparecer entre os confirmados")

## 6.4. Telas da área do responsável

O responsável cadastra a própria conta, as crianças e um segundo responsável (que vê a criança, mas só o responsável principal altera os dados dela).

![Início do responsável](imagem/telas/fig06.jpg "Figura 6. Início do responsável com criança cadastrada")

![Meus dados e crianças](imagem/telas/fig07.jpg "Figura 7. Meus dados e crianças: adicionando uma criança")

![Criança salva](imagem/telas/fig08.jpg "Figura 8. Criança salva no cadastro")

![Segundo responsável: busca por CPF](imagem/telas/fig09.jpg "Figura 9. Segundo responsável: busca por CPF preenche os dados")

![Segundo responsável vendo a criança](imagem/telas/fig10.jpg "Figura 10. Segundo responsável enxergando a criança, com o aviso de que só o principal altera")

![Início do segundo responsável](imagem/telas/fig16.jpg "Figura 16. Início do segundo responsável (Júlia)")

## 6.5. Telas de funcionários e serviços (coordenação)

![Lista de funcionários](imagem/telas/fig41.jpg "Figura 41. Lista de funcionários: função, papéis, supervisor e nível de acesso")

![Novo funcionário](imagem/telas/fig42.jpg "Figura 42. Novo funcionário")

![Funcionário cadastrado](imagem/telas/fig43.jpg "Figura 43. Funcionário cadastrado")

![Editar funcionário](imagem/telas/fig44.jpg "Figura 44. Editar funcionário")

![Confirmação de exclusão de funcionário](imagem/telas/fig45.jpg "Figura 45. Confirmação de exclusão (não permitida se houver atendimentos ou eventos)")

![Confirmação de exclusão, segundo teste](imagem/telas/fig46.jpg "Figura 46. Confirmação de exclusão, segundo teste")

![Funcionário removido](imagem/telas/fig47.jpg "Figura 47. Funcionário removido")

![Catálogo de serviços](imagem/telas/fig48.jpg "Figura 48. Catálogo de serviços (coordenação)")

![Editar serviço](imagem/telas/fig49.jpg "Figura 49. Editar serviço")

![Serviço alterado](imagem/telas/fig50.jpg "Figura 50. Serviço alterado antes de salvar")

![Lista após a edição](imagem/telas/fig51.jpg "Figura 51. Catálogo com as informações atualizadas")

![Confirmação de exclusão de serviço](imagem/telas/fig52.jpg "Figura 52. Confirmação antes de remover um serviço")

![Bloqueio: serviço em uso](imagem/telas/fig53.jpg "Figura 53. Bloqueio: serviço contratado em algum evento não pode ser removido")

![Bloqueio, segundo teste](imagem/telas/fig54.jpg "Figura 54. Bloqueio de exclusão, segundo teste")

![Serviços na visão do monitor](imagem/telas/fig55.jpg "Figura 55. Serviços na visão do monitor: somente leitura")

## 6.6. Evidências do banco de dados

Os prints mostram o banco preenchido no MySQL Workbench.

![Quantidade de linhas por tabela](imagem/telas/fig56.jpg "Figura 56. Quantidade de linhas por tabela: as 18 tabelas têm dados, por exemplo PESSOA (10), RESPONSAVEL (5), CRIANCA (7), FUNCIONARIO (5), ACESSO (5), ATENDIMENTO (7), EVENTO (5) e SERVICO (5)")

![Tabela PESSOA](imagem/telas/fig57.jpg "Figura 57. Tabela PESSOA")

![Tabela TELEFONE_PESSOA](imagem/telas/fig58.jpg "Figura 58. Tabela TELEFONE_PESSOA")

![Tabela ACESSO](imagem/telas/fig59.jpg "Figura 59. Tabela ACESSO: senha guardada como hash")

![Tabela FUNCIONARIO](imagem/telas/fig60.jpg "Figura 60. Tabela FUNCIONARIO")

![Tabela MONITOR](imagem/telas/fig61.jpg "Figura 61. Tabela MONITOR")

![Tabela CRIANCA](imagem/telas/fig62.jpg "Figura 62. Tabela CRIANCA")

![Tabela RESPONSAVEL](imagem/telas/fig63.png "Figura 63. Tabela RESPONSAVEL")

![Tabela RECEPCIONISTA](imagem/telas/fig64.png "Figura 64. Tabela RECEPCIONISTA")

![Tabela RESPONSAVEL_ADICIONAL](imagem/telas/fig65.png "Figura 65. Tabela RESPONSAVEL_ADICIONAL")

![Tabela ATENDIMENTO](imagem/telas/fig66.png "Figura 66. Tabela ATENDIMENTO")

![Tabela ACOMPANHA](imagem/telas/fig67.png "Figura 67. Tabela ACOMPANHA")

![Tabela EVENTO](imagem/telas/fig68.png "Figura 68. Tabela EVENTO")

![Tabela FICHA_BRIEFING](imagem/telas/fig69.png "Figura 69. Tabela FICHA_BRIEFING")

![Tabela CHECKLIST_EVENTO](imagem/telas/fig70.png "Figura 70. Tabela CHECKLIST_EVENTO")

![Tabela SERVICO](imagem/telas/fig71.png "Figura 71. Tabela SERVICO")

![Tabela PARTICIPACAO](imagem/telas/fig72.png "Figura 72. Tabela PARTICIPACAO")

![Tabela CONTRATACAO](imagem/telas/fig73.png "Figura 73. Tabela CONTRATACAO")

![Tabela CONFIGURACAO](imagem/telas/fig74.png "Figura 74. Tabela CONFIGURACAO")