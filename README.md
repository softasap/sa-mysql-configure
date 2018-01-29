sa-mysql-configure
==================
[![Build Status](https://travis-ci.org/softasap/sa-mysql-configure.svg?branch=master)](https://travis-ci.org/softasap/sa-mysql-configure)


Example of usage:

Simple

```YAML

     - {
         role: "sa-mysql-configure",
         mysql_root_user: root,
         mysql_root_password: devroot,
         mysql_databases: "{{my_mysql_databases}}",
         mysql_users: "{{my_mysql_users}}"
       }


```

Advanced

see box-example for full featured lamp install.

```YAML

    - my_mysql_databases:
       - name: app_db
         encoding: utf8
         collation: utf8_general_ci
    - my_mysql_users:
       - name: app_user
         host: "%"
         password: dYud8LHBBptGN96LSn0e
         priv: "app_db.*:ALL"

...

     - {
         role: "sa-mysql-configure",
          mysql_root_user: root,
          mysql_root_password: devroot,
          mysql_databases: "{{my_mysql_databases}}",
          mysql_users: "{{my_mysql_users}}"
       }


```


Usage with ansible galaxy workflow
----------------------------------

If you installed the `sa-mysql-configure` role using the command


`
   ansible-galaxy install softasap.sa-php-fpm
`

the role will be available in the folder `library/softasap.sa-php-fpm`
Please adjust the path accordingly.

```YAML

     - {
         role: "softasap.sa-mysql-configure"
       }

```




Copyright and license
---------------------

Code is dual licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) and the [MIT License] (http://opensource.org/licenses/MIT). Choose the one that suits you best.

Reach us:

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)

Join gitter discussion channel at [Gitter](https://gitter.im/softasap)

Discover other roles at  http://www.softasap.com/roles/registry_generated.html

visit our blog at http://www.softasap.com/blog/archive.html
