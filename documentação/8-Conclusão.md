## 8. Conclusão

<span style="color:red">Pré-requisitos: <a href="6-Interface-Sistema.md"> Projeto da Solução</a></span>

**Síntese dos resultados.** O trabalho partiu da observação de dois processos da Brinquedoteca Barreiro, atendimento da criança e festas e eventos, que dependiam de papel e de muitas idas e vindas entre responsável, recepção, monitoria e equipe. A análise AS-IS apontou os gargalos (4 atividades manuais na entrada, cobrança dependente da liberação do monitor, orçamento sem padrão e sem repasse formal à equipe). A proposta TO-BE foi implementada no sistema **Virando a Folha**, com front-end, back-end e banco relacional de 18 tabelas na 3FN.

O sistema entrega, com evidências nas telas e no banco:

- entrada rápida da criança, com horário automático;
- cobrança calculada por minuto, com faixa de preço e 5% de desconto para irmãos, e controle de pagamento;
- orçamento de festa em quatro passos, com ficha de briefing, serviços, equipe escalada e checklists antes e depois do evento;
- área do responsável para cadastrar a conta, as crianças (com observações como alergias) e pedir festas;
- acesso por perfil, senhas com hash e regras de integridade garantidas pelo banco (por exemplo, serviço contratado e funcionário com histórico não podem ser excluídos).

**Limitações.**

- Os ganhos esperados (menos fila, menos atraso, menos retrabalho e menos desencontro nas festas) vêm da análise dos processos e **ainda não foram medidos na prática**.
- O pagamento em si, o acompanhamento da criança e a preparação das festas continuam presenciais; o sistema registra e calcula, mas não cobra.
- O sistema foi demonstrado com dados e usuários de teste.


**Novas linhas de estudo**
- Medir os indicadores da seção 7 com dados reais e comparar com a situação anterior (AS-IS).
- Hospedar o sistema online.
- Incluir relatórios, como faturamento por período e serviços mais contratados.
- Incluir verificador de cpf.