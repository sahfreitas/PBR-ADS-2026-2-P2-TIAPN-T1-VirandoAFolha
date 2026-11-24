# Introdução


**Virando a Folha** é um sistema web que troca os controles em papel da **Brinquedoteca Barreiro** (Belo Horizonte – MG) por uma aplicação única, com acesso separado para a equipe e para os responsáveis pelas crianças. O lema do projeto é *"Do papel ao digital, porque brincar é coisa séria"*.

O trabalho foi desenvolvido na disciplina **Trabalho Interdisciplinar: Aplicações para Processos de Negócio** (Sistemas de Informação, PUC Minas), sob orientação do professor Gleisson Albergaria Amaral, como atividade de extensão universitária.

**Equipe:**

- Luísa Braga Nery de Lima
- Maria Luiza de Oliveira Pinholate
- Melissa Vitor da Silva
- Sara da Cruz Freitas
- Sophia Emanuelle de Morais dos Santos

**Repositório:** <https://github.com/sahfreitas/PBR-ADS-2026-2-P2-TIAPN-T1-VirandoAFolha.git>


## Problema

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

**Objetivo geral:** desenvolver um sistema web com banco de dados relacional que resolva os problemas dos dois processos acima, substituindo as fichas e anotações em papel da Brinquedoteca Barreiro.

**Objetivos específicos:**

1. Modelar em BPMN os dois processos atuais (AS-IS) e as propostas de melhoria (TO-BE).
2. Registrar entrada e saída das crianças com cálculo automático do valor pelo tempo de permanência e controle do pagamento.
3. Padronizar o orçamento de festas com ficha de briefing, serviços contratados, equipe escalada e checklists antes e depois do evento.
4. Manter um banco de dados integrado, com controle de acesso por perfil (coordenação, recepção, monitoria e responsável).

## Justificativa


A observação dos processos na prática mostrou que o BPMN deixa gargalos e retrabalho visíveis, e que melhorar nem sempre exige tecnologia complexa: padronizar o atendimento, registrar horários e usar checklists já reduz erros. Por isso a solução foi pensada para a realidade da Brinquedoteca e evita recursos desnecessariamente complexos.

O sistema também dá aos responsáveis um canal próprio para cadastrar as crianças e pedir o orçamento da festa sem sair de casa, o que tira trabalho do balcão. Os ganhos esperados vêm da análise dos processos e **ainda não foram medidos na prática**.

> ⚠️ **FALTA:** o template sugere apoiar a justificativa em questionário, entrevista ou dados estatísticos. Se o grupo tiver anotações da reunião de 25/09/2026 (ou respostas da equipe), resuma-as aqui.

## Público-Alvo

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