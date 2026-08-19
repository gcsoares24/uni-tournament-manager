# Tournament Manager: base de dados relacional para torneios de e-sports

![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat&logo=mariadb&logoColor=white)

> 📖 Quick note in English: This README is also available in English. To access it, just click [here](README.md).

## Sobre o projeto

Tournament Manager é uma base de dados relacional que modela um sistema de gestão de torneios de e-sports, cobrindo torneios, edições, fases, encontros (rondas), jogadores, treinadores, equipas, arenas virtuais, bilhética (online e presencial) e espectadores. Foi desenvolvido no âmbito da disciplina de **Bases de Dados**, no ano letivo 2024/25, por [Guilherme Soares](https://github.com/gcsoares24) e [Vitória Correia](https://github.com/vitoriateixeiracorreia), com contribuições de Duarte Soares e Diogo Almeida.

### Funcionalidades
- **Torneios e edições** — um torneio (`Torneio`) agrupa várias edições anuais (`Edicao`), cada uma com um valor total de prémios, um número máximo de equipas e um jogo associado (`Jogo`).
- **Fases e encontros** — as edições dividem-se em fases (`Fase`: fase de grupos, quartos, meias e final) com encontros no formato melhor de 3/5/7 (`Encontro`), que por sua vez são compostos por rondas (`Ronda`) disputadas em arenas virtuais (`ArenaVirtual`).
- **Equipas e plantel** — as equipas (`Equipa`) têm membros (`MembroEquipa`) que são jogadores (`Jogador`) ou treinadores (`Treinador`), modelados através de uma relação IS-A.
- **Papel do jogador por ronda** — os jogadores podem assumir diferentes papéis/especialidades (`Especialidade`, ex.: Atacante, Meio-campo, Defensor) e estão limitados a um único papel por ronda de cada encontro (`PapelPorRonda`).
- **Bilhética** — os bilhetes (`Bilhete`) são online (`BilheteOnline`, associados a uma plataforma de streaming `PlataformaOnline`) ou presenciais (`BilhetePresencial`, associados a um recinto `Recinto` e a uma zona de lugares `Zona`), através de uma relação IS-A.
- **Espectadores** — os espectadores (`Espectador`) podem acumular créditos e recomendar outros espectadores (relação autorreferenciada).
- **Dados de exemplo e queries** — o script de DDL inclui instruções `INSERT` de exemplo, e um script de DML separado contém um conjunto de queries analíticas (`SELECT` com joins, subinterrogações, operadores de conjuntos e agregação) sobre o esquema.

### Stack tecnológica
- **Linguagem**: SQL (DDL para criação do esquema, DML para as interrogações)
- **SGBD**: MySQL / MariaDB (usa colunas `DATETIME`, `CHECK` constraints inline e o comando `SOURCE` do cliente)
- **Documentação**: esquema entidade-relacionamento exportado em PDF (`SCHEMA.pdf`)

## Estrutura do repositório
- `DDL/BD-2425-E1_bd013_TP12.sql` — script de criação das tabelas (`DROP TABLE` + `CREATE TABLE` + `INSERT`s de exemplo) e o respetivo relatório (`.pdf`).
- `DML.sql` — conjunto de queries `SELECT` que respondem ao enunciado de manipulação de dados do projeto.
- `SCHEMA.pdf` — o diagrama entidade-relacionamento da base de dados.

## Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/gcsoares24/BD-tournament-manager.git
   ```
2. Importe o esquema da base de dados (num cliente MySQL/MariaDB):
   ```sql
   SOURCE DDL/BD-2425-E1_bd013_TP12.sql;
   ```
3. Execute as queries de `DML.sql` sobre o esquema populado.

## Autores
- **Guilherme Soares** ([@gcsoares24](https://github.com/gcsoares24)) — desenvolvimento e modelagem da base de dados.
- **Vitória Correia** ([@vitoriateixeiracorreia](https://github.com/vitoriateixeiracorreia))
- Duarte Soares, Diogo Almeida — contribuidores na etapa de DDL.

## Licença

Este projeto é de caráter académico e não possui uma licença específica. Caso deseje utilizá-lo, entre em contacto com o autor.
