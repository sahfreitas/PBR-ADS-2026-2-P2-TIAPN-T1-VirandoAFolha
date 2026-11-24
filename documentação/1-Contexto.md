# Introdução

Texto descritivo com a visão geral do projeto abordado. Inclui o contexto, o problema, os objetivos, a justificativa e o público-alvo do projeto.

**Virando a Folha** é um sistema web que troca os controles em papel da **Brinquedoteca Barreiro** (Belo Horizonte – MG) por uma aplicação única, com acesso separado para a equipe e para os responsáveis pelas crianças. O lema do projeto é *"Do papel ao digital, porque brincar é coisa séria"*.

O trabalho foi desenvolvido na disciplina **Trabalho Interdisciplinar: Aplicações para Processos de Negócio** (Sistemas de Informação, PUC Minas), sob orientação do professor Gleisson Albergaria Amaral, como atividade de extensão universitária.

**Equipe:**

- Luísa Braga Nery de Lima
- Maria Luiza de Oliveira Pinholate
- Melissa Vitor da Silva
- Sara da Cruz Freitas
- Sophia Emanuelle de Morais dos Santos

**Repositório:** <https://github.com/melissavitor/VirandoAFolha>

> ⚠️ **CONFERIR:** o link do repositório acima veio do documento de evidências da Atividade 4. Se o repositório oficial da entrega for outro, troque o link aqui.

## Problema
Nesse momento você deve apresentar o problema que a sua aplicação deve  resolver. No entanto, não é a hora de comentar sobre a aplicação.

Descreva também o contexto em que essa aplicação será usada, se  houver: empresa, tecnologias, etc. Novamente, descreva apenas o que de  fato existir, pois ainda não é a hora de apresentar requisitos  detalhados ou projetos.

Nesse momento, o grupo pode optar por fazer uso  de ferramentas como Design Thinking, que permite um olhar de ponta a ponta para o problema.

> **Links Úteis**:
> - [Objetivos, Problema de pesquisa e Justificativa](https://medium.com/@versioparole/objetivos-problema-de-pesquisa-e-justificativa-c98c8233b9c3)
> - [Matriz Certezas, Suposições e Dúvidas](https://medium.com/educa%C3%A7%C3%A3o-fora-da-caixa/matriz-certezas-suposi%C3%A7%C3%B5es-e-d%C3%BAvidas-fa2263633655)
> - [Brainstorming](https://www.euax.com.br/2018/09/brainstorming/)

**Contexto.** A Brinquedoteca Barreiro atua em recreação e entretenimento infantil e fica na Rua Rodolfo Jacob, 76, bairro Barreiro, em Belo Horizonte. A equipe é formada por coordenação, recepção e monitoria. Hoje as fichas de entrada e saída, a cobrança por tempo, os orçamentos de festas e a escala da equipe são controlados em papel.

**Como o problema foi levantado.** O grupo enviou uma carta de apresentação (08/09/2026), fez uma visita com reunião com a equipe em 25/09/2026, observou o dia a dia e conversou com os responsáveis. Dessa observação saíram dois processos com excesso de tarefas manuais e idas e vindas entre as pessoas envolvidas:

1. **Atendimento, permanência e saída da criança.**
   - A recepção realiza 4 atividades manuais em sequência só para registrar a entrada: realizar atendimento, verificar informações, registrar entrada e encaminhar a criança.
   - Na saída, o cálculo do valor só começa depois que o tempo termina e o monitor libera a criança.
   - Consequência: fila na recepção, atraso na entrada e na saída e retrabalho na comunicação dos horários entre responsável, recepção e monitor.
2. **Solicitação, contratação e realização de festas e eventos.**
   - O orçamento não segue um padrão, e a negociação repete passos quando a data pedida não está disponível.
   - Depois que os serviços são registrados, o evento segue para a equipe sem repasse formal das informações e sem checklists do espaço.
   - Consequência: risco de desencontro sobre o que foi contratado, atraso no atendimento inicial e falhas na conferência do espaço antes e depois da festa.

## Objetivos

Aqui você deve descrever os objetivos do trabalho indicando que o objetivo geral é desenvolver um software para solucionar o problema apresentado acima. 

Apresente também alguns (pelo menos 2) objetivos específicos dependendo de onde você vai querer concentrar a sua prática investigativa, ou como você vai aprofundar no seu trabalho.
 
> **Links Úteis**:
> - [Objetivo geral e objetivo específico: como fazer e quais verbos utilizar](https://blog.mettzer.com/diferenca-entre-objetivo-geral-e-objetivo-especifico/)

**Objetivo geral:** desenvolver um sistema web com banco de dados relacional que resolva os problemas dos dois processos acima, substituindo as fichas e anotações em papel da Brinquedoteca Barreiro.

**Objetivos específicos:**

1. Modelar em BPMN os dois processos atuais (AS-IS) e as propostas de melhoria (TO-BE).
2. Registrar entrada e saída das crianças com cálculo automático do valor pelo tempo de permanência e controle do pagamento.
3. Padronizar o orçamento de festas com ficha de briefing, serviços contratados, equipe escalada e checklists antes e depois do evento.
4. Manter um banco de dados integrado, com controle de acesso por perfil (coordenação, recepção, monitoria e responsável).

## Justificativa

Descreva a importância ou a motivação para trabalhar com esta aplicação que você escolheu. Indique as razões pelas quais você escolheu seus objetivos específicos ou as razões para aprofundar em certos aspectos do software.

O grupo de trabalho pode fazer uso de questionários, entrevistas e dados estatísticos, que podem ser apresentados, com o objetivo de esclarecer detalhes do problema que será abordado pelo grupo.

> **Links Úteis**:
> - [Como montar a justificativa](https://guiadamonografia.com.br/como-montar-justificativa-do-tcc/)

A observação dos processos na prática mostrou que o BPMN deixa gargalos e retrabalho visíveis, e que melhorar nem sempre exige tecnologia complexa: padronizar o atendimento, registrar horários e usar checklists já reduz erros. Por isso a solução foi pensada para a realidade da Brinquedoteca e evita recursos desnecessariamente complexos.

O sistema também dá aos responsáveis um canal próprio para cadastrar as crianças e pedir o orçamento da festa sem sair de casa, o que tira trabalho do balcão. Os ganhos esperados vêm da análise dos processos e **ainda não foram medidos na prática**.

> ⚠️ **FALTA:** o template sugere apoiar a justificativa em questionário, entrevista ou dados estatísticos. Se o grupo tiver anotações da reunião de 25/09/2026 (ou respostas da equipe), resuma-as aqui.

## Público-Alvo

Descreva quem serão as pessoas que usarão a sua aplicação indicando os diferentes perfis. O objetivo aqui não é definir quem serão os clientes ou quais serão os papéis dos usuários na aplicação. A ideia é, dentro do possível, conhecer um pouco mais sobre o perfil dos usuários: conhecimentos prévios, relação com a tecnologia, relações
hierárquicas, etc.

Adicione informações sobre o público-alvo por meio de uma descrição textual, diagramas de personas e mapa de stakeholders.

> **Links Úteis**:
> - [Público-alvo](https://blog.hotmart.com/pt-br/publico-alvo/)
> - [Como definir o público alvo](https://exame.com/pme/5-dicas-essenciais-para-definir-o-publico-alvo-do-seu-negocio/)
> - [Público-alvo: o que é, tipos, como definir seu público e exemplos](https://klickpages.com.br/blog/publico-alvo-o-que-e/)
> - [Qual a diferença entre público-alvo e persona?](https://rockcontent.com/blog/diferenca-publico-alvo-e-persona/)

O sistema atende dois grupos: a **equipe da Brinquedoteca**, que usa o sistema no balcão e nas festas, e as **famílias**, que usam a área do responsável. A equipe tem uma hierarquia simples, com coordenação acima da recepção e da monitoria (no banco, cada funcionário pode ter um supervisor).

| Grupo | Perfil | Relação com o sistema |
| --- | --- | --- |
| Equipe | Coordenação | Acompanha o dia, gerencia funcionários e o catálogo de serviços e vê todos os módulos |
| Equipe | Recepção | Cadastra famílias, registra entradas e saídas, cobra e monta os orçamentos de festas |
| Equipe | Monitoria | Acompanha as crianças e executa a escala e os checklists das festas |
| Famílias | Responsável | Cadastra a própria conta e as crianças, acompanha seus eventos e solicita festas |

**Mapa de stakeholders (resumo):**

| Parte interessada | Interesse no sistema |
| --- | --- |
| Coordenação da Brinquedoteca | Controle do dia, da equipe e dos serviços oferecidos |
| Recepção | Entrada rápida, cobrança correta e orçamentos padronizados |
| Monitores | Saber quais festas e checklists estão sob sua responsabilidade |
| Responsáveis | Segurança dos dados da criança e facilidade para pedir festas |
| Crianças | Beneficiárias indiretas: atendimento mais ágil e informações importantes (alergias, cuidados) registradas |
| PUC Minas / professor | Avaliação da atividade de extensão |

**Acesso e facilidade de uso.** O sistema funciona tanto no **celular** quanto no **computador**, e é rápido e fácil de acessar. Isso atende os dois grupos: a equipe pode usá-lo no balcão ou durante as festas, e os responsáveis podem acessá-lo de onde estiverem, sem precisar instalar nada.

> ⚠️ **FALTA (opcional):** o conhecimento prévio da equipe e das famílias com tecnologia (por exemplo, se a equipe já usava computador no balcão antes do sistema) não aparece nos arquivos enviados. Se o grupo anotou isso na visita, acrescente aqui. Se o grupo fez diagramas de personas, coloque a imagem aqui também.