## 3. Modelagem dos Processos de Negócio

Foram modelados **dois processos** da Brinquedoteca Barreiro, observados na visita de 25/09/2026:

1. Atendimento, permanência e saída da criança
2. Solicitação, contratação e realização de festas e eventos

### 3.1. Modelagem da situação atual (Modelagem AS IS)

Hoje a Brinquedoteca não usa um sistema: as fichas de entrada e saída, a cobrança por tempo, os orçamentos de festas e a escala da equipe são controlados em papel.

**Processo 1: atendimento, permanência e saída da criança.** O responsável chega com a criança e solicita o atendimento. A recepção realiza o atendimento, verifica as informações da criança, registra a entrada e encaminha a criança para a brinquedoteca. O monitor recebe a criança e a acompanha durante a permanência. Quando o tempo termina, o monitor libera a criança para retirada e só então a recepção calcula o valor, informa ao responsável e confirma o pagamento. Depois disso a saída é liberada e o responsável retira a criança.

> **Notação dos diagramas:** o responsável (processo 1) e o cliente (processo 2) ficam em uma **piscina separada**, porque estão fora da Brinquedoteca. As raias (Recepção, Monitor, Equipe) ficam dentro da piscina da Brinquedoteca Barreiro. Dentro de uma piscina, as atividades se ligam por **fluxo de sequência** (linha cheia). Entre as piscinas, a comunicação é feita por **fluxo de mensagem** (linha pontilhada).
>
> ⚠️ **CONFERIR:** estes 4 diagramas foram **redesenhados** (cliente em piscina separada, ligações por mensagem). Para ligar as piscinas foram acrescentados eventos de mensagem (início, envio e espera de resposta). As imagens antigas, com o cliente como raia, estão em `imagem/bpmn-versao-anterior/`. Se a Atividade 02 já foi entregue e avaliada com a versão antiga, avise o professor ou mantenha as duas versões coerentes. Os arquivos editáveis são os `.svg` da pasta `imagem/`.

![BPMN AS-IS do processo de atendimento](imagem/bpmn-p1-as-is.png "BPMN AS-IS: processo de atendimento da Brinquedoteca")

**Processo 2: festas e eventos.** O cliente pede informações sobre a festa e a recepção apresenta as opções. A recepção verifica a disponibilidade da data. Se a data não está disponível, informa a indisponibilidade, oferece outras datas e repete a verificação. Se está disponível, levanta as informações do evento, define os serviços contratados e elabora o orçamento. O cliente analisa e decide: se não aprova, a negociação é encerrada. Se aprova, a recepção confirma a reserva e registra os serviços contratados. A equipe prepara o espaço, realiza o evento e organiza o espaço depois, **sem repasse formal das informações e sem checklists**.

![BPMN AS-IS de festas e eventos](imagem/bpmn-p2-as-is.png "BPMN AS-IS: organização de festas e eventos")

**Gargalos identificados:**

| Processo | Gargalo | Evidência observada | Impacto |
| --- | --- | --- | --- |
| 1 | Excesso de etapas burocráticas na entrada e dependência do monitor para iniciar a cobrança na saída | A recepção fazia 4 atividades manuais seguidas para registrar a entrada (realizar atendimento, verificar informações, registrar entrada e encaminhar criança); o cálculo só começava após o fim do tempo e a liberação pelo monitor | Filas na recepção, atraso na entrada e na saída e retrabalho na comunicação dos horários |
| 2 | Falta de padronização no orçamento e ausência de repasse estruturado das informações à equipe | A negociação dependia de vários passos manuais e repetições quando a data estava indisponível; depois de registrar os serviços, o evento ia para a equipe sem repasse formal nem checklists | Risco de desencontro sobre o que foi contratado, atrasos no atendimento inicial e falhas na conferência do espaço antes e depois da festa |

### 3.2. Descrição geral da proposta (Modelagem TO BE)

Tendo identificado os gargalos dos modelos AS IS, apresentem uma descrição da proposta de solução, buscando maior eficiência com a introdução da tecnologia. Abordem também os limites dessa solução e o seu alinhamento com as estratégias e objetivos do contexto de negócio escolhido. 
Colem aqui os modelos da solução proposta (modelo TO BE) elaborados com o apoio da ferramenta baseada em BPMN utilizada na disciplina.
Cada processo identificado deve ter seu modelo TO-BE específico. Descrevam as oportunidades de melhoria de cada processo da solução proposta.

A proposta é um sistema web simples, que apoia a equipe sem sobrecarregá-la, com procedimento padronizado de atendimento e registro de horários e dados em um banco único.

**Processo 1 (TO-BE).** A entrada fica rápida: a recepção só identifica ou cadastra a criança e registra o horário de entrada, que é marcado automaticamente. A recepção e o monitor passam a ser ligados pelo registro dos horários. Quando o responsável pede a retirada, a recepção registra o horário de saída e o sistema calcula o valor na hora, sem esperar a liberação do monitor. A recepção informa o valor, confirma o pagamento e encerra o atendimento.

![BPMN TO-BE do processo de atendimento](imagem/bpmn-p1-to-be.png "BPMN TO-BE: processo de atendimento da Brinquedoteca")

*Oportunidades de melhoria:* menos atividades manuais na entrada (de 4 atividades para 2: identificar ou cadastrar a criança e registrar o horário de entrada), cobrança disparada ao fim do tempo, menos fila, menos atraso e menos retrabalho.

**Processo 2 (TO-BE).** A recepção registra as informações do evento e consulta a agenda. Com a data disponível, seleciona a modalidade e os serviços e elabora o orçamento; sem a data, oferece outras datas. O cliente analisa o orçamento. Se aprova, a recepção confirma a reserva, registra os serviços contratados e **disponibiliza as informações para a equipe** por meio de uma ficha de briefing. A equipe faz o **checklist pré-evento**, prepara o espaço, realiza o evento, faz o **checklist pós-evento** e organiza o espaço.

![BPMN TO-BE de festas e eventos](imagem/bpmn-p2-to-be.png "BPMN TO-BE: organização de festas e eventos")

*Oportunidades de melhoria:* formulário de cadastro e orçamento padronizados, ficha de briefing repassada à equipe e checklists antes e depois da festa, com menos desencontro sobre o que foi contratado.

**Limites da solução:** o sistema cobre o registro, o cálculo, o orçamento, a escala e os checklists. O pagamento em si (o responsável paga no balcão), o acompanhamento da criança pelo monitor e a preparação e realização da festa continuam sendo atividades presenciais. Os ganhos esperados vêm da análise dos processos e **ainda não foram medidos na prática**.

**Alinhamento com o negócio:** a proposta busca menos tarefas manuais, informações mais organizadas, menos erros e mais eficiência, que são os objetivos da proposta para o atendimento e as festas.

### 3.3. Modelagem dos processos

[PROCESSO 1 - Atendimento, permanência e saída da criança](./processo/processo-1-atendimento-da-crianca.md "Detalhamento do Processo 1.")

[PROCESSO 2 - Solicitação, contratação e realização de festas e eventos](./processo/processo-2-festas-e-eventos.md "Detalhamento do Processo 2.")

<!-- LINKS DO TEMPLATE (mantidos para consulta; o projeto só tem 2 processos):
[PROCESSO 3 - Nome do Processo](./processos/processo-3-nome-do-processo.md "Detalhamento do Processo 3.")
[PROCESSO 4 - Nome do Processo](./processos/processo-4-nome-do-processo.md "Detalhamento do Processo 4.")
-->

> ⚠️ **CONFERIR:** os arquivos `processo-3-nome-do-processo.md` e `processo-4-nome-do-processo.md` ficaram na pasta `processo/` só como modelo. O projeto tem 2 processos; se o professor não exigir 4, apague esses dois arquivos.

> ⚠️ **FALTA:** o BPMN foi feito na ferramenta usada na disciplina. Se existir o arquivo-fonte (`.bpmn`) ou o link do modelo, coloque aqui para facilitar correções.
