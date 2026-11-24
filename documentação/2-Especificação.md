# Especificações do Projeto

<span style="color:red">Pré-requisitos: <a href="1-Contexto.md"> Documentação de Contexto</a></span>

Esta especificação parte dos dois processos mapeados na visita à Brinquedoteca Barreiro: o atendimento da criança (entrada, permanência e saída) e a organização de festas e eventos. Os dois estão detalhados em [3-Modelagem-Processos-Negócio](3-Modelagem-Processos-Negócio.md), com os problemas do processo atual (AS-IS) que o sistema precisa resolver.

Para transformar esses problemas em requisitos, foram usadas as seguintes técnicas:

1. **Personas:** cinco personas fictícias, criadas a partir dos papéis das raias do BPMN, que representam quem ganha agilidade com o sistema.
2. **Histórias de usuário:** o que cada persona precisa fazer e por quê, no formato "Eu como... quero... para...".
3. **Requisitos funcionais (RF):** o que o sistema deve fazer, derivado das histórias.
4. **Requisitos não funcionais (RNF):** qualidades esperadas, como desempenho, usabilidade e acesso pelo celular e pelo computador.
5. **Restrições do projeto:** prazo, tecnologias e outros limites que definem o escopo.

## Personas

<!-- EXEMPLO DO TEMPLATE (mantido para consulta):
Pedro Paulo tem 26 anos, é arquiteto recém-formado e autônomo. Pensa em se desenvolver profissionalmente através de um mestrado fora do país, pois adora viajar, é solteiro e sempre quis fazer um intercâmbio. Está buscando uma agência que o ajude a encontrar universidades na Europa que aceitem alunos estrangeiros.
-->

Enumere e detalhe as personas da sua solução. Para tanto, baseie-se tanto nos documentos disponibilizados na disciplina e/ou nos seguintes links:

> **Links Úteis**:
> - [Rock Content](https://rockcontent.com/blog/personas/)
> - [Hotmart](https://blog.hotmart.com/pt-br/como-criar-persona-negocio/)
> - [O que é persona?](https://resultadosdigitais.com.br/blog/persona-o-que-e/)
> - [Persona x Público-alvo](https://flammo.com.br/blog/persona-e-publico-alvo-qual-a-diferenca/)
> - [Mapa de Empatia](https://resultadosdigitais.com.br/blog/mapa-da-empatia/)
> - [Mapa de Stalkeholders](https://www.racecomunicacao.com.br/blog/como-fazer-o-mapeamento-de-stakeholders/)
>
Lembre-se que você deve ser enumerar e descrever precisamente e personalizada todos os clientes ideais que sua solução almeja.

As personas abaixo representam quem mais se beneficia com um atendimento mais ágil na Brinquedoteca Barreiro. Elas partem dos papéis que aparecem nas raias dos dois processos BPMN (recepção, monitor, coordenação e responsável) e dos problemas observados no processo atual (AS-IS).

![Personas do Virando a Folha](imagem/personas.png "Personas do Virando a Folha")

### Persona 1: Larissa Moreira, 29 anos (Recepcionista)

Trabalha no balcão. Recebe o responsável, cadastra a criança, registra a entrada e a saída e cobra pelo tempo. Também monta os orçamentos das festas. Usa celular o tempo todo e o computador no trabalho para tarefas simples.

- **Frustrações hoje:** Faz 4 atividades manuais seguidas só para registrar a entrada; a fila cresce no balcão nos horários de pico; só calcula o valor depois que o monitor libera a criança; cada orçamento de festa sai de um jeito.
- **Objetivos:** Registrar a entrada em poucos cliques; cobrar o valor certo, sem conta de cabeça; montar orçamentos padronizados.
- **O que o sistema entrega:** Cadastro da família numa tela, entrada com horário automático, valor calculado por minuto, orçamento de festa em 4 passos. (requisitos RF-005, RF-006, RF-008, RF-009, RF-012).

### Persona 2: Rodrigo Teixeira, 23 anos (Monitor)

Acompanha as crianças durante a permanência e trabalha nas festas. Chega para o turno e precisa saber o que vai acontecer no dia. Jovem, à vontade com o celular.

- **Frustrações hoje:** Recebe a festa sem repasse formal das informações; não tem checklist do espaço antes e depois do evento; precisa avisar a recepção de cada saída; descobre o horário de chegada na festa em cima da hora.
- **Objetivos:** Saber quais festas e horários são dele; seguir um checklist antes e depois da festa; liberar a criança sem idas e vindas.
- **O que o sistema entrega:** “Minha escala” com função e horário de chegada, checklists de antes e depois da festa, lista de crianças brincando agora. (requisitos RF-007, RF-014, RF-015).

### Persona 3: Marta Ribeiro, 45 anos (Coordenadora)

Coordena a equipe e os serviços oferecidos. Acompanha o dia e fecha as festas com os responsáveis. Usa computador e celular no dia a dia, mas não é da área de TI.

- **Frustrações hoje:** Não tem uma visão única do dia: crianças presentes, valores a receber e festas; fichas e anotações em papel espalhadas; orçamentos sem padrão e sem registro da equipe escalada; controle do acesso da equipe é manual.
- **Objetivos:** Ver o dia em um só lugar; manter equipe, funções e serviços atualizados; confirmar festas com tudo registrado.
- **O que o sistema entrega:** Painel inicial com indicadores, gestão de funcionários e acessos, catálogo de serviços, confirmação e cancelamento de eventos. (requisitos RF-013, RF-016, RF-017, RF-018).

### Persona 4: Camila Andrade, 34 anos (Responsável (mãe))

Mãe de dois filhos pequenos e trabalha fora. Leva as crianças à Brinquedoteca e já pensou em fazer a festa de aniversário lá. Usa o celular para tudo, inclusive compras e banco.

- **Frustrações hoje:** Espera na fila para a entrada e a saída; só sabe o valor a pagar na hora de ir embora; precisa ir ao balcão para pedir e negociar a festa; teme que a equipe não saiba da alergia de um dos filhos.
- **Objetivos:** Cadastrar as crianças uma vez, com as observações; saber o valor e pagar rápido; pedir a festa sem sair de casa e acompanhar o pedido.
- **O que o sistema entrega:** Conta própria com cadastro das crianças e observações, solicitação de evento em passos e acompanhamento da situação. (requisitos RF-002, RF-003, RF-011).

### Persona 5: Paulo Andrade, 38 anos (Segundo responsável (pai))

Pai das crianças. Algumas vezes quem leva e busca é ele, não a mãe. Usa o celular no dia a dia.

- **Frustrações hoje:** Depende da mãe para a equipe aceitar a retirada; não sabe o que está cadastrado sobre os filhos; precisa refazer informações a cada visita.
- **Objetivos:** Retirar e acompanhar a criança sem refazer o cadastro; ver as informações importantes dos filhos.
- **O que o sistema entrega:** Vínculo como segundo responsável por busca de CPF: ele enxerga a criança, mas só o responsável principal altera os dados. (requisitos RF-004).

**Resumo do ganho de agilidade:**

| Persona | Perfil no sistema | Onde ganha agilidade |
| --- | --- | --- |
| Larissa (recepcionista) | Recepção | Entrada em poucos passos, valor calculado sozinho e orçamento padronizado |
| Rodrigo (monitor) | Monitoria | Escala e checklists à mão, sem repasse informal |
| Marta (coordenadora) | Coordenação | Painel do dia, equipe e serviços em um só lugar |
| Camila (mãe) | Responsável | Cadastro e pedido de festa sem ir ao balcão |
| Paulo (pai) | Segundo responsável | Retirada e consulta da criança sem refazer o cadastro |

> ⚠️ **CONFERIR:** as personas são **fictícias**. Nomes, idades e detalhes pessoais foram inventados a partir dos papéis e dos problemas levantados na visita de 25/09/2026. Se o grupo tiver observações reais (por exemplo, o perfil das pessoas da equipe), ajuste os textos. O conhecimento de cada persona com tecnologia é uma suposição.

## Histórias de Usuários

Com base na análise das personas forma identificadas as seguintes histórias de usuários:

<!-- EXEMPLO DO TEMPLATE (mantido para consulta):
|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE` |PARA ... `MOTIVO/VALOR`                 |
|--------------------|------------------------------------|----------------------------------------|
|Usuário do sistema  | Registrar minhas tarefas           | Não esquecer de fazê-las               |
|Administrador       | Alterar permissões                 | Permitir que possam administrar contas |
-->

|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE` |PARA ... `MOTIVO/VALOR`                 |
|--------------------|------------------------------------|----------------------------------------|
| **Responsável** (Camila) | Criar minha conta com meus dados, endereço e telefones | Cadastrar meus filhos e pedir festas sem ir ao balcão |
| Responsável | Cadastrar minhas crianças com observações (alergias, cuidados especiais) | A equipe saber o que é importante sobre cada criança |
| Responsável | Vincular um segundo responsável à criança | Outra pessoa da família poder acompanhar a criança |
| **Segundo responsável** (Paulo) | Ver a criança vinculada a mim, com as observações | Buscá-la e acompanhá-la sem refazer o cadastro |
| Responsável | Solicitar uma festa informando data, convidados e o que espero dela | Receber o orçamento sem negociar tudo pessoalmente |
| Responsável | Ver a situação dos meus eventos (em análise, orçamento, confirmado) | Saber em que pé está o pedido |
| **Recepção** (Larissa) | Cadastrar a família e as crianças numa única tela | Reduzir as etapas de entrada |
| Recepção | Registrar a entrada da criança com o horário automático | Não depender de anotação em papel |
| Recepção | Registrar a saída e ver o valor calculado pelo tempo, com desconto para irmãos | Cobrar corretamente e sem demora |
| Recepção | Confirmar o pagamento ou deixar pendente | Controlar o que já foi pago |
| Recepção | Montar o orçamento da festa em passos (dados, briefing, serviços e equipe) | Padronizar a negociação e não esquecer informações |
| Recepção | Confirmar ou cancelar o evento | Fechar a reserva depois da decisão do cliente |
| **Monitoria** (Rodrigo) | Ver a minha escala de festas com horário de chegada e checklist | Chegar preparado e saber o que conferir |
| Monitoria | Marcar os itens do checklist antes e depois da festa | Garantir que o espaço foi conferido |
| **Coordenação** (Marta) | Ver o painel do dia (crianças presentes, valores a receber, eventos) | Acompanhar a operação em um só lugar |
| Coordenação | Cadastrar e editar funcionários, funções, papéis, supervisor e acesso | Controlar quem usa o sistema e com que permissão |
| Coordenação | Manter o catálogo de serviços das festas | Oferecer valores e serviços atualizados nos orçamentos |

> ⚠️ **CONFERIR:** as histórias foram escritas a partir das funcionalidades que aparecem nas evidências da Atividade 4. Se o grupo já tinha histórias de usuário aprovadas, use essas.

Apresente aqui as histórias de usuário que são relevantes para o projeto de sua solução. As Histórias de Usuário consistem em uma ferramenta poderosa para a compreensão e elicitação dos requisitos funcionais e não funcionais da sua aplicação. Se possível, agrupe as histórias de usuário por contexto, para facilitar consultas recorrentes à essa parte do documento.

> **Links Úteis**:
> - [Histórias de usuários com exemplos e template](https://www.atlassian.com/br/agile/project-management/user-stories)
> - [Como escrever boas histórias de usuário (User Stories)](https://medium.com/vertice/como-escrever-boas-users-stories-hist%C3%B3rias-de-usu%C3%A1rios-b29c75043fac)
> - [User Stories: requisitos que humanos entendem](https://www.luiztools.com.br/post/user-stories-descricao-de-requisitos-que-humanos-entendem/)
> - [Histórias de Usuários: mais exemplos](https://www.reqview.com/doc/user-stories-example.html)
> - [9 Common User Story Mistakes](https://airfocus.com/blog/user-story-mistakes/)



## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

**Técnica de priorização aplicada:** a prioridade foi definida pela ligação com os processos TO-BE.
- **ALTA:** o requisito sustenta diretamente uma atividade dos processos mapeados (entrada, saída e cobrança; orçamento, confirmação e checklists de festas) ou é condição para usar o sistema (acesso, segurança).
- **MÉDIA:** o requisito dá suporte aos processos (cadastros, escala, catálogo, gestão da equipe).
- **BAIXA:** o requisito é de conveniência (painel inicial, atalhos).

> ⚠️ **CONFERIR:** se o grupo usou outra técnica na disciplina (MoSCoW, votação, matriz de impacto), troque o texto acima e ajuste as prioridades.

### Requisitos Funcionais


|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| Permitir login por CPF e senha, com perfis de acesso diferentes (coordenação, funcionário e responsável) | ALTA |
|RF-002| Permitir que o responsável crie a própria conta (dados pessoais, endereço, telefones e senha), validando senhas diferentes e CPF já cadastrado | ALTA |
|RF-003| Permitir cadastrar e editar crianças (nome, data de nascimento e observações), pelo responsável ou pela equipe | ALTA |
|RF-004| Permitir vincular um segundo responsável à criança por busca de CPF; ele vê a criança, mas só o responsável principal altera os dados | MÉDIA |
|RF-005| Permitir cadastrar a família (responsável e crianças) numa única tela e consultar e editar a lista de clientes | MÉDIA |
|RF-006| Registrar a entrada da criança escolhendo a criança, o recepcionista e os monitores, com horário de entrada automático | ALTA |
|RF-007| Listar as crianças presentes com tempo decorrido e valor parcial, e permitir desfazer uma entrada feita por engano | MÉDIA |
|RF-008| Registrar a saída e calcular o valor por minuto, com faixa de preço pelo tempo de permanência e desconto de 5% para irmãos | ALTA |
|RF-009| Confirmar o pagamento do atendimento ou deixá-lo pendente, e manter o histórico de atendimentos | ALTA |
|RF-010| Disponibilizar calculadora de valor e tabela de preços por faixa de tempo | BAIXA |
|RF-011| Permitir que o responsável solicite um evento (dados da festa e briefing) e acompanhe a situação do pedido | ALTA |
|RF-012| Permitir à equipe montar o evento em quatro passos (dados da festa, briefing, serviços e equipe), com total do orçamento | ALTA |
|RF-013| Confirmar ou cancelar o evento (situação orçamento, confirmado ou cancelado) e filtrar a lista de eventos por situação | ALTA |
|RF-014| Gerar e manter checklists de antes e depois da festa, com inclusão e remoção de itens | ALTA |
|RF-015| Escalar funcionários no evento (função na festa e horário de chegada) e mostrar a "Minha escala" ao monitor | MÉDIA |
|RF-016| Manter o catálogo de serviços (cadastrar, editar e excluir), bloqueando a exclusão de serviço contratado em algum evento | MÉDIA |
|RF-017| Manter funcionários (cadastrar, editar e excluir) com função, papéis, supervisor e acesso, bloqueando a exclusão de quem tem atendimentos ou eventos | MÉDIA |
|RF-018| Exibir painel inicial por perfil, com atalhos, indicadores do dia e próximos eventos | BAIXA |

### Requisitos não Funcionais


|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| As senhas devem ser armazenadas com hash, nunca em texto puro | ALTA |
|RNF-002| Cada perfil só pode ver e usar as áreas e ações permitidas a ele | ALTA |
|RNF-003| A integridade dos dados deve ser garantida pelo banco, com restrições CHECK, chaves estrangeiras e triggers (por exemplo, CPF com 11 dígitos, hora de saída maior que a de entrada, no máximo um responsável adicional por criança) | ALTA |
|RNF-004| Os dados devem ficar em um banco relacional MySQL, normalizado até a 3FN | MÉDIA |
|RNF-005| O sistema deve ser simples de usar no balcão, sem recursos desnecessariamente complexos | MÉDIA |
|RNF-006| Parâmetros do sistema, como o valor da hora, devem ficar em tabela de configuração, e não fixos no código | BAIXA |

> ⚠️ **CONFERIR:** o grupo não enviou requisitos de desempenho, responsividade (celular) nem navegadores suportados. Se houve decisão sobre isso, acrescente RNFs.

Com base nas Histórias de Usuário, enumere os requisitos da sua solução. Classifique esses requisitos em dois grupos:

- [Requisitos Funcionais
 (RF)](https://pt.wikipedia.org/wiki/Requisito_funcional):
 correspondem a uma funcionalidade que deve estar presente na
  plataforma (ex: cadastro de usuário).
- [Requisitos Não Funcionais
  (RNF)](https://pt.wikipedia.org/wiki/Requisito_n%C3%A3o_funcional):
  correspondem a uma característica técnica, seja de usabilidade,
  desempenho, confiabilidade, segurança ou outro (ex: suporte a
  dispositivos iOS e Android).
Lembre-se que cada requisito deve corresponder à uma e somente uma
característica alvo da sua solução. Além disso, certifique-se de que
todos os aspectos capturados nas Histórias de Usuário foram cobertos.

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.


|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deve ser entregue até o final do semestre letivo de 2026 |
|02| A aplicação deve ter front-end, back-end e banco de dados relacional, incorporando os processos mapeados nas etapas anteriores |
|03| O banco deve ser MySQL; como o MySQL não permite CHECK que consulte outras linhas ou a data atual, essas regras foram implementadas com triggers |
|04| A solução deve ser simples e adequada à realidade da Brinquedoteca, evitando recursos desnecessariamente complexos |
|05| O trabalho é feito em grupo de cinco integrantes e depende do acesso à equipe da Brinquedoteca para validar os processos |

Enumere as restrições à sua solução. Lembre-se de que as restrições geralmente limitam a solução candidata.

> **Links Úteis**:
> - [O que são Requisitos Funcionais e Requisitos Não Funcionais?](https://codificar.com.br/requisitos-funcionais-nao-funcionais/)
> - [O que são requisitos funcionais e requisitos não funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/)