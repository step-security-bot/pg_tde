# Install `pg_tde` on Red Hat Enterprise Linux and derivatives

The packages for the tech preview `pg_tde` are available in the experimental repository for Percona Distribution for PostgreSQL 17. 

Check the [list of supported platforms](install.md#__tabbed_1_2).

This tutorial shows how to install `pg_tde` with [Percona Distribution for PostgreSQL](https://docs.percona.com/postgresql/latest/index.html).

## Preconditions

### Enable / disable modules

For RHEL8/Oracle Linux 8/Rocky Linux 8, disable the ``postgresql``  and ``llvm-toolset``modules:    

```bash
sudo dnf module disable postgresql llvm-toolset
```

### Install `percona-release`

You need the `percona-release` repository management tool that enables the desired Percona repository for you.

1. Install `percona-release`:

    ```bash
    sudo yum -y install https://repo.percona.com/yum/percona-release-latest.noarch.rpm 
    ```

2. Enable the repository

    ```bash
    sudo percona-release enable-only ppg-{{pgversion17}} experimental
    ```

## Install `pg_tde`

1. Install Percona Distribution for PostgreSQL 17 and the required packages, run the following command:

    ```bash
    sudo yum -y install percona-postgresql-client-common percona-postgresql-common percona-postgresql-server-dev-all percona-postgresql17 percona-postgresql17-contrib percona-postgresql17-devel percona-postgresql17-libs
    ```
    
2. Install `pg_tde` packages
        
    ```bash
    sudo yum install percona-pg_tde_17
    ```


## Next steps

[Setup](setup.md){.md-button}
