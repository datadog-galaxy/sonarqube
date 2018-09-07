# Ansible Role: SonarQube

Installs and configures SonarQube service on RHEL/CentOS server.

## Requirements

No special requirements; note that this role requires root access, so either run it in a playbook with a global `become: yes`, or invoke the role in your playbook like:

    - hosts: database
      roles:
        - role: geerlingguy.postgresql
          become: yes

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    version: 7.3

You can set version of SonarQube which you need to install.

    database_user: sonarqube
    database_password: mypassword

Set the database username and password.

    database_driver: jdbc:driver

Set JDBC driver URL. SonarQube supports Microsoft SQL, PostgreSQL or MySQL database servers. 

## Dependencies

SonarQube requires to have Java (Oracle JRE 8 or OpenJDK 8), thus it depends on `datadog-galaxy.oracle_java`.

Also it depends on database, but as SonarQube supports multiple database servers it's users choice to install it beforehand.

## Example Playbook

    - hosts: sonarqube
      become: yes
      roles:
        - sonarqube

## License

BSD
