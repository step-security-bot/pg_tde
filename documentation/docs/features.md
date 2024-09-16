# Build comparison

We provide `pg_tde` builds for both PostgreSQL Community and [Percona Server for PostgreSQL](https://docs.percona.com/postgresql/17/). The difference between the builds is in the set of included features which in its turn depends on the Storage Manager API. While PostgreSQL Community uses the default Storage Manager API, Percona Server for PostgreSQL extends the Storage Manager API enabling to integrate custom storage managers.

## Features

The following table provides the differences between the builds:

| PostgreSQL Community build  | Percona Server for PostgreSQL build <br> (in addition to features included in the PostgreSQL Community build)|
|----------------------|-------------------------------|
| Table encryption: <br> - data tables, <br> - TOAST tables <br> - temporary tables created during the database operation.<br><br> Metadata of those tables is not encrypted. | Index data encryption for encrypted tables |
| Write-Ahead Log (WAL) encryption of data in encrypted tables | Write-Ahead Log (WAL) encryption of data for encrypted and non-encrypted tables  |
| Multi-tenancy support|  |   
| Table-level granularity | | 
| Key management via: <br> - HashiCorp Vault; <br> - Local keyfile | 

## Future releases

The following is planned for future releases of `pg_tde`:

* Logical replication support
* KMIP integration for key management

<i warning>:material-alert: Warning:</i> Note that introducing encryption/decryption affects performance. Our benchmark tests show less than 10% performance overhead for most situations. However, in some specific applications such as those using JSONB operations, performance degradation might be higher.

[Get started](install.md){.md-button}