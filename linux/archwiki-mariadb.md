# MariaDB

**MariaDB** is a reliable, high performance and full-featured database server which aims to be an 'always Free, backward compatible, drop-in' replacement to **MySQL**. Since 2013 MariaDB is Arch Linux's default implementation of MySQL.

## Installation

**MariaDB** is the default implementation of MySQL in Arch Linux, provided with the **mariadb** package.

Install **mariadb**, and run the following command _before starting_ the `mariadb.service`

```sh
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
```

> Note: Before continuing, it is recommended to [[MariaDB-setup#Improve the initial security|improve the initial security]] of MariaDB installation

Now `mariadb.service` can be **started** and/or **enabled**.

## Configuration

Once you have started the MariaDB server and added a root account, you may want to change the default configuration.

To log in as `root` on the MariaDB server, use the following command:

```sh
mariadb -u root -p
```

> Note: The default password is empty. Press `Enter` to log in.

### Add user

Create a new user takes two steps: create the user; grant privileges. In the below example, the user _monty_ with _some_pass_ is being created, then granted permissions to the database _mydb_:

```sh
mariadb -u root -p

CREATE USER 'monty'@'localhost' IDENTIFIED BY 'some_pass';
GRANT ALL PRIVILEGES ON mydb.* to 'monty'@'localhost';
quit
```

### Enable auto-completion

> Note: Enabling this feature can make the client initialization longer.

The MariaDB client completion feature is disable by default. To enable it system-wide edit `/etc/my.cnf.d/mysql-clients.cnf`, and add `auto-rehash` under `mariadb`. Note that this must not be placed under `mysqld`. Completion will be enable next time you run the MariaDB client.

## Security

### Improve the initial security

The `mariadb-secure-installation` command will interactively guide you through a number of recommended security measures, such as removing anonymous accounts and removing the test database

```sh
mariadb-secure-installation
```
