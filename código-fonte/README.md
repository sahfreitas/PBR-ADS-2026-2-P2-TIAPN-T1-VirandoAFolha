# Código-fonte do projeto

Aqui ficam os arquivos-fonte do **Virando a Folha**, o sistema web de gestão da Brinquedoteca Barreiro: back-end (Node.js + Express), banco de dados (MySQL) e front-end (HTML, CSS e JavaScript).

## Tecnologias

| Camada | Tecnologia |
|---|---|
| Back-end | Node.js, Express 5 |
| Banco de dados | MySQL 8.0 (driver `mysql2`) |
| Front-end | HTML, CSS e JavaScript puro, servidos pelo próprio Express |
| Configuração | `dotenv` (arquivo `.env`) |
| Segurança | Senhas com hash `scrypt` (nativo do Node) e sessão por cookie |

## Estrutura de pastas

```text
código-fonte/
├── server.js            # ponto de entrada: monta o Express e registra as rotas
├── db.js                # conexão (pool) com o MySQL, lida do .env
├── package.json
├── .env.example         # modelo das variáveis de ambiente
├── db/database/
│   ├── schema.sql       # cria o banco "brinquedoteca" e as 18 tabelas
│   ├── seed.sql         # dados fictícios para teste
│   └── consultas.sql    # consultas SQL da disciplina de Banco de Dados
├── routes/              # uma rota por assunto (API REST em JSON)
│   ├── auth.js          # login, logout, criar conta, trocar senha
│   ├── painel.js        # números do painel inicial
│   ├── responsaveis.js  # cadastro de responsáveis
│   ├── criancas.js      # cadastro de crianças e responsável adicional
│   ├── atendimentos.js  # entrada, saída, cobrança e pagamento
│   ├── eventos.js       # eventos, agenda, status e checklist
│   ├── servicos.js      # catálogo de serviços
│   ├── funcionarios.js  # funcionários, recepcionistas, monitores e acessos
│   └── configuracoes.js # regras de cobrança
├── utils/               # regras e funções compartilhadas
│   ├── sessao.js        # login, cookie, hash de senha e permissões
│   ├── acessos.js       # CPF + senha + perfil (tabela ACESSO)
│   ├── portal.js        # o que o responsável logado pode acessar
│   ├── cobranca.js      # cálculo do valor do atendimento
│   ├── transacao.js     # várias gravações como uma só (tudo ou nada)
│   ├── pessoa.js        # validações de PESSOA
│   └── erros.js         # erros do banco e da validação em mensagens amigáveis
└── public/              # front-end
    ├── *.html           # telas do sistema
    └── assets/
        ├── comum/       # CSS base, cabeçalho, componentes, fontes e scripts compartilhados
        └── <tela>/      # css/ e js/ de cada tela
```

## Telas

| Tela | Arquivo | Para que serve |
|---|---|---|
| Entrar | `login.html` | Login por CPF e senha |
| Criar conta | `criar-conta.html` | O responsável cria o próprio acesso |
| Início | `index.html` | Painel com os principais números |
| Cadastro | `cadastro.html` | Cadastro de responsáveis e crianças |
| Clientes | `clientes.html` | Consulta de responsáveis e crianças |
| Atendimentos | `atendimentos.html` | Entrada e saída da criança, cobrança e pagamento |
| Eventos | `eventos.html` e `evento.html` | Lista, agenda e detalhe do evento (status e checklist) |
| Serviços | `servicos.html` | Catálogo de serviços |
| Funcionários | `funcionarios.html` | Equipe e acessos (somente coordenação) |

## Perfis de acesso

O acesso é feito por **CPF e senha**, e cada pessoa tem um perfil guardado na tabela `ACESSO`:

| Perfil | O que pode fazer |
|---|---|
| `ADMIN` (coordenação) | Tudo, incluindo alterar serviços e gerenciar funcionários |
| `FUNCIONARIO` | Usar o sistema e consultar; não altera serviços nem funcionários |
| `RESPONSAVEL` | Portal do responsável: vê e edita só o próprio cadastro, as próprias crianças e os próprios eventos |

A sessão fica no servidor e dura 8 horas. Se o servidor reiniciar, é preciso entrar de novo.

## Regras de negócio

* **Cobrança do atendimento:** o tempo é contado por minuto e o valor da hora depende do tempo total da visita (R$ 35/h para menos de 2h, caindo até R$ 28/h para 5h ou mais). Irmãos têm 5% de desconto no valor da hora. A regra está em `utils/cobranca.js`.
* **Gravações em transação:** operações com várias tabelas usam `utils/transacao.js`; se uma falhar, nada é gravado.
* **Validações no banco:** triggers e restrições do MySQL barram dados inválidos, e o back-end converte esses erros em mensagens claras para o usuário.

## Banco de dados

O banco `brinquedoteca` tem 18 tabelas, entre elas `PESSOA`, `RESPONSAVEL`, `FUNCIONARIO`, `CRIANCA`, `ATENDIMENTO`, `EVENTO`, `SERVICO` e `ACESSO`. Os scripts ficam em `db/database/`:

1. `schema.sql`: cria o banco e as tabelas (**apaga e recria** o banco, se ele já existir)
2. `seed.sql`: insere dados fictícios de teste
3. `consultas.sql`: consultas SQL de exemplo, para executar uma por vez

## Como executar

Pré-requisitos: Node.js 18 ou superior e MySQL 8.0 em execução.

```bash
cd código-fonte
cp .env.example .env     # preencha DB_USER e DB_PASSWORD com os dados do seu MySQL
npm install
npm run dev
```

Antes de iniciar, rode `schema.sql` e depois `seed.sql` no MySQL Workbench. Acesse **http://localhost:3000**. O terminal deve mostrar `Conectado ao MySQL`.

## Telas do sistema

![Login](../documentação/imagem/tela-login.png)

![Painel inicial](../documentação/imagem/tela-inicio.png)

![Cadastro](../documentação/imagem/tela-cadastro.png)

![Atendimentos](../documentação/imagem/tela-atendimentos.png)

![Eventos](../documentação/imagem/tela-eventos.png)

![Portal do responsável](../documentação/imagem/tela-portal-responsavel.png)