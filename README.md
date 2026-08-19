# Tournament Manager: relational database for e-sports tournaments

![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat&logo=mariadb&logoColor=white)

> 📖 Quick note in Portuguese: You can also read this README in Portuguese. To do so, just access [here](README.pt.md).

## About the project

Tournament Manager is a relational database that models an e-sports tournament management system, covering tournaments, editions, phases, matches (rounds), players, coaches, teams, virtual arenas, ticketing (online and in-person) and spectators. It was developed for the **Database Management** (Bases de Dados) course, academic year 2024/25, by [Guilherme Soares](https://github.com/gcsoares24) and [Vitória Correia](https://github.com/vitoriateixeiracorreia), with contributions from Duarte Soares and Diogo Almeida.

### Features
- **Tournaments & editions** — a tournament (`Torneio`) groups multiple yearly editions (`Edicao`), each with a prize pool, a maximum number of teams and a linked game (`Jogo`).
- **Phases & matches** — editions are split into phases (`Fase`: group stage, quarter-, semi- and final) with best-of-3/5/7 matches (`Encontro`), which in turn are made up of rounds (`Ronda`) played in virtual arenas (`ArenaVirtual`).
- **Teams & roster** — teams (`Equipa`) have members (`MembroEquipa`) that are either players (`Jogador`) or coaches (`Treinador`), modeled with an IS-A relationship.
- **Player roles per round** — players can take on different roles/specialties (`Especialidade`, e.g. Attacker, Mid, Defender) and are limited to a single role per round of a given match (`PapelPorRonda`).
- **Ticketing** — tickets (`Bilhete`) are either online (`BilheteOnline`, tied to a streaming platform `PlataformaOnline`) or in-person (`BilhetePresencial`, tied to a venue `Recinto` and a seating zone `Zona`), via an IS-A relationship.
- **Spectators** — spectators (`Espectador`) can accumulate credits and recommend other spectators (self-referencing relationship).
- **Sample data & queries** — the DDL script ships with sample `INSERT` statements, and a separate DML script contains a set of analytical `SELECT` queries (joins, subqueries, set operators, aggregation) over the schema.

### Tech stack
- **Language**: SQL (DDL for schema creation, DML for queries)
- **DBMS**: MySQL / MariaDB (uses `DATETIME` columns, inline `CHECK` constraints and the `SOURCE` client command)
- **Documentation**: entity-relationship schema exported as PDF (`SCHEMA.pdf`)

## Repository structure
- `DDL/BD-2425-E1_bd013_TP12.sql` — table creation script (`DROP TABLE` + `CREATE TABLE` + sample `INSERT`s) and its accompanying report (`.pdf`).
- `DML.sql` — a set of `SELECT` queries answering the project's data-manipulation assignment.
- `SCHEMA.pdf` — the entity-relationship diagram for the database.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/gcsoares24/BD-tournament-manager.git
   ```
2. Import the database schema (in a MySQL/MariaDB client):
   ```sql
   SOURCE DDL/BD-2425-E1_bd013_TP12.sql;
   ```
3. Run the queries in `DML.sql` against the populated schema.

## Authors
- **Guilherme Soares** ([@gcsoares24](https://github.com/gcsoares24)) — database development and modeling.
- **Vitória Correia** ([@vitoriateixeiracorreia](https://github.com/vitoriateixeiracorreia))
- Duarte Soares, Diogo Almeida — contributors to the DDL stage.

## License

This project is academic in nature and does not have a specific license. If you wish to use it, please contact the author.
