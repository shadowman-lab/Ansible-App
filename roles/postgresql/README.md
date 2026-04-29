<!-- This was created with Claude Code -->

postgresql
==========

An Ansible role for postgresql.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **pgsql**: Variable used in: {{ pgsql.packages_list_el_8 }}
  - Default: `{'pgdata': "{{ overrides_pgsql_pgdata | default('/var/lib/pgsql/data') }}", 'packages_list_el_8': ['python39', 'python39-devel', 'python3-psycopg2', 'postgresql-server'], 'packages_list_el_9': ['python3', 'python3-devel', 'python3-psycopg2', 'postgresql-server'], 'db': [{'name': "{{ postgres.db_name | default('default_db') }}", 'user': "{{ postgres.user.name | default('db_user') }}", 'password': "{{ postgres.user.password | default('db_password') }}"}, {'name': "{{ postgres.keycloak.db_name | default('default_db') }}", 'user': "{{ postgres.keycloak.name | default('db_user') }}", 'password': "{{ postgres.keycloak.password | default('db_password') }}"}, {'name': "{{ postgres.wildfly.db_name | default('default_db') }}", 'user': "{{ postgres.wildfly.name | default('db_user') }}", 'password': "{{ postgres.wildfly.password | default('db_password') }}"}]}`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: postgresql
      vars:
        pgsql: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
