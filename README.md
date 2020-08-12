LAMP Automated
================

Test automated LAMP setup using Vagrant &amp; Puppet

**Additional documentation to install puppet modules which will install apache and my sql**

The puppet binary has a module subcommand that will connect to the Puppet Forge to download Puppet modules and their dependencies. The commands we used will install Puppet Labs’ apache and mysql modules (and their dependencies). We’re also passing the --target-dir argument that will tell the puppet module subcommand to install the module into our shared directory (instead of Puppet’s default module path).

Install apache framework:
```puppet module install puppetlabs/apache --target-dir /puppet/modules/```


Install MYSQL framework:
```puppet module install puppetlabs/mysql --target-dir /puppet/modules/```



Check for the puppet modules:
```ls /puppet/modules/
apache  concat  firewall  mysql  stdli
```


we are using puppet module to install these modules, but there are a multitude of other methods you can use (from downloading the modules directly out of `Github` to using a tool like `librarian-puppet`). The point is that we need to ultimately get the modules into the modules directory in our shared puppet folder
