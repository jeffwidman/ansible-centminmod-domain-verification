centminmod-domain-verification
=========

This is an Ansible helper role for testing/verifying that individual domains are
configured properly on servers setup using the [Centminmod](http://centminmod.com/)
bash script. If a domain is not configured properly, the playbook immediately fails.

If you're using Centminmod, the following roles play well together:
  - **[centminmod wrapper](https://github.com/jeffwidman/ansible-centminmod)** (handles basic install + tuning common configuration settings)
  - **[mariadb](https://github.com/jeffwidman/ansible-mariadb)** (configures common my.cnf settings)
  - **[centminmod-domain-verification](https://github.com/jeffwidman/ansible-centminmod-domain-verification)** (tests that individual domains are configured properly)
  - **[php-fpm-pool](https://github.com/jeffwidman/ansible-php-fpm-pool)** (for creating/managing individual php-fpm pools for each PHP app)

Example meta file:
----------------
To use this, in your domain-specific role, add the role as a meta
dependency and pass the `domain` variable.

    ---
    # meta file for jeffwidman_com role

    dependencies:
      - { role: centminmod-domain-verification,
            domain: jeffwidman.com
            }

License
-------

MIT

Author Information
------------------

Jeff Widman jeff@jeffwidman.com
