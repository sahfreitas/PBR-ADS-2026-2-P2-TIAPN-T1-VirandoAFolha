# Virando a Folha

`SISTEMAS DE INFORMAÇÃO`

`TRABALHO INTERDISCIPLINAR`

`2º SEMESTRE`

**Virando a Folha** é um sistema web de gestão para a **Brinquedoteca Barreiro**, criado para facilitar a rotina de quem cuida do espaço. Hoje, controlar quem são as crianças e seus responsáveis, quem foi atendido e quando, quais eventos estão marcados e quais serviços são oferecidos exige anotações e controles manuais, que se perdem e dificultam a consulta. O sistema reúne essas informações em um só lugar, de forma simples e organizada.

Com ele, a equipe cadastra responsáveis e crianças, registra atendimentos, organiza eventos e serviços, gerencia funcionários e acompanha um painel com os principais números da brinquedoteca. O acesso é feito por login, com permissões diferentes para a coordenação (administração), para os funcionários e para os responsáveis, que enxergam apenas o que é deles.

**Tecnologias:** Node.js, Express, MySQL, HTML, CSS e JavaScript.

## Integrantes

* Luísa Braga Nery de Lima
* Maria Luiza de Oliveira Pinholate
* Melissa Vitor da Silva
* Sara da Cruz Freitas
* Sophia Emanuelle de Morais dos Santos

## Orientador

* Gleisson Albergaria Amaral

## Instruções de utilização

### Pré-requisitos

* [Node.js](https://nodejs.org/) (versão 18 ou superior)
* [MySQL 8.0](https://dev.mysql.com/downloads/) em execução (o banco usa recursos do MySQL 8; não funciona no MySQL 5.7 nem no MariaDB)

### 1. Criar o banco de dados

No MySQL Workbench (ou outro cliente), execute os arquivos abaixo **nesta ordem**:

1. `código-fonte/db/database/schema.sql`: cria o banco `brinquedoteca` e as tabelas (**apaga e recria** o banco, se ele já existir)
2. `código-fonte/db/database/seed.sql`: insere dados fictícios para teste

### 2. Configurar o ambiente

Dentro da pasta `código-fonte`, crie um arquivo `.env` a partir do exemplo e preencha com os dados do seu MySQL:

```bash
cd código-fonte
cp .env.example .env
```

```env
PORT=3000
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=sua_senha
DB_NAME=brinquedoteca
```

> O arquivo `.env` não é versionado (está no `.gitignore`). Cada pessoa cria o seu.

### 3. Instalar as dependências e executar

Ainda dentro da pasta `código-fonte`:

```bash
npm install
npm run dev
```

Acesse **http://localhost:3000**. Se tudo estiver certo, o terminal mostra `Conectado ao MySQL`.

> Execute sempre de dentro da pasta `código-fonte`, pois é ali que ficam o `package.json`, o `.env` e a pasta `public`.

# Documentação

<ol>
<li><a href="documentação/1-Contexto.md"> Documentação de Contexto</a></li>
<li><a href="documentação/2-Especificação.md"> Especificação do Projeto</a></li>
<li><a href="documentação/3-Modelagem-Processos-Negócio.md"> Modelagem dos Processos de Negócio</a></li>
<li><a href="documentação/4-Projeto-Solucao.md"> Projeto da Solução</a></li>
<li><a href="documentação/5-Planejamento-Projeto.md"> Planejamento do Projeto</a></li>
<li><a href="documentação/6-Interface-Sistema.md"> Interface do Sistema</a></li>
<li><a href="documentação/7-Indicadores.md"> Indicadores</a></li>
<li><a href="documentação/8-Conclusão.md"> Conclusão</a></li>
<li><a href="documentação/9-Referências.md"> Referências</a></li>
</ol>

# Código

<li><a href="código-fonte/README.md"> Código Fonte</a></li>

# Apresentação

<li><a href="documentação/apresentação/README.md"> Apresentação da solução</a></li>
<li><a href="documentação/vídeo/README.md"> Vídeo</a></li>


## Histórico de versões

* 1.0.0
    * Sistema web com cadastro de responsáveis e crianças, atendimentos, eventos, serviços, funcionários, painel e login com perfis de acesso.
* 0.1.1
    * CHANGE: Atualização das documentações. Código permaneceu inalterado.
* 0.1.0
    * Implementação da funcionalidade X pertencente ao processo P.
* 0.0.1
    * Trabalhando na modelagem do processo de negócio.