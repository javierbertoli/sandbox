sandbox
=======

Probably nothing useful here... Just to try things on github

```puppet
class {'bacula:
  manage_client   => true,
  manage_storage  => false,
  manage_director => true,
  manage_console  => false,
}
```
        
* Install a specific version of bacula storage package
        
```puppet
class { 'bacula':
  manage_storage  => true,
  version         => '1.0.1',
}
```
                                            
```puppet
class { 'bacula':
  manage_client   => false,
  manage_storage  => true,
  version         => '1.0.1',
}
```

* Disable bacula service.

```puppet
class { 'bacula':
  manage_client   => false,
  manage_director => true,
  director_source => [ "puppet:///modules/netmanagers/bacula/bacula-dir.conf-${hostname}",
                       "puppet:///modules/example42/bacula/bacula-dir.conf" ],
}
```
