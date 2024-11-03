# ansible_pgsql

This is an ansible role set that configures a master and standby active/passive architecture PostgreSQL cluster.

This role assumes the following:

1. The operating system in use is RHEL 9.x
2. The base RHEL subscription repositories are used
3. The data drive is 150GB
4. The data drive is located at /dev/sda
5. The data drive will be mounted to /opt for PostgreSQL
6. The PostgreSQL installation path is /opt/postgresql/data
7. PostgreSQL 13 is the version to be installed
8. SELinux is enforcing

Based on these assumptions the roles produce an installation that is

1. Customised to install a /opt/posgresql/data
2. Has a customised systemd unit file to run the daemon
3. Uses the default installation 'postgres' account to run the daemon
4. Uses the default 'postgres' database user that connects to the default 'postgres' database
5. Secures the postgresql configuration in the following way
   - Sets user password encryption to SCRAM-SHA-256
   - Enables TLS with a self-signed certificate
   - Enables logical WAL replication to the secondary (standby) server

# NOTES
1. Securing the installation has not been completed yet in the roles.
2. Creating the secondary (standby) server has not been completed yet in the roles.
3. Enabling logical WAL replication has not been completed yet in the roles.
