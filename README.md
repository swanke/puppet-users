# USERS Module

# This module is moved to https://github.com/phononet/puppet-users.git

## Quick Start

Create user Bob

```puppet
node default {
  users::manage { 'bob': }
}
```

Set password for user Bob

```puppet
node default {
  users::manage { 'bob':
    uid      => '1100',
    gid      => '1100',
    home     => '/home',
    shell    => '/bin/bash',
    ensure   => 'present',
    comment  => 'Admin user',
    password => '<shadow password>',
  }
}
```

Add group

```puppet
node default {
  users::group { 'admin' }
  users::manage { 'bob': groups => 'admin' }
}
```
