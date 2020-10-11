<p align="center">
  <img width="500px" src="https://media.githubusercontent.com/media/cybertec-postgresql/zheap/master/img/zheap.png"/>
  <br/>
  <i>Reinvented PostreSQL Storage</i>
</p>

<hr/>

<p align="center">
  <a href="#about">About</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#status">Status</a> •
  <a href="#documentation">Documentation</a> •
  <a href="#benchmarks">Benchmarks</a> •
  <a href="#contact">Contact</a>
</p>

[![Postgres 13](https://img.shields.io/badge/postgres-13-blue.svg)](https://github.com/postgres/postgres/tree/REL_13_STABLE)
[![Status](https://img.shields.io/badge/status-early%20development-orange)](https://github.com/cybertec-postgresql/postgres/tree/REL_13_ZHEAP)

## About

_zheap_ is a way to **keep table bloat under control** by implementing a new PostgreSQL storage engine capable of running **`UPDATE`-intense workloads** more efficiently. The project was originally started by [EnterpriseDB](https://www.enterprisedb.com/).

To make _zheap_ ready for production, we are proud to announce that our partners at [Heroic Labs](https://heroiclabs.com/) have committed to **fund the development** of _zheap_ and **release all code to the community**. [CYBERTEC](https://www.cybertec-postgresql.com/en/) has decided to **double the funding amount**, and to put up additional expertise and manpower to move _zheap_ forward.

### Why?

Table bloat describes the phenomenon of tables and / or indices growing in size, even if the amount of data stored in the database stays constant. If one wants to support transactions it is necessary not to overwrite data in case it is rolled back.

PostgreSQL copies rows on `UPDATE` and stores them in the same table. Stale rows are periodically garbage-collected by an automatic process called [VACUUM](https://www.postgresql.org/docs/current/sql-vacuum.html). Problems start to crop up in `UPDATE`-heavy workloads, as VACUUM might not always be able to keep up.

### How?

CYBERTEC has started a [series of blog posts](https://www.cybertec-postgresql.com/en/zheap-reinvented-postgresql-storage/) that go into the design-goals of _zheap_.

## Contributing

There are a number of active branches that will be merged together once they reach maturity.

- [Logical decoding](https://github.com/cybertec-postgresql/postgres/tree/zheap_logical_decoding)
- [Undo record set](https://github.com/cybertec-postgresql/postgres/tree/undo-record-set-ah)
- [Rebase on PostgreSQL 13](https://github.com/cybertec-postgresql/postgres/tree/REL_13_ZHEAP)

## Status

- 12-10-2020: [Most regression tests are passing](https://github.com/cybertec-postgresql/postgres/blob/REL_13_ZHEAP/src/test/README.md), but write-speeds are still low.

## Documentation

Managed through [GitHub Wiki](https://github.com/cybertec-postgresql/zheap/wiki).

## Benchmarks

Will be conducted at a later date, as no attempts at performance tuning have been made yet.

## Contact

- [Development](https://github.com/cybertec-postgresql/postgres/issues)
- [Business](https://www.cybertec-postgresql.com/en/contact/)
