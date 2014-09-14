# apache

This module installs httpd and ensures httpd stays running. If httpd stops it will restart it on next Puppet
run. This goes in the init.pp file.

class apache { 

    package { httpd:
        ensure => installed,
    }

    service { httpd:
        ensure => running,
        enable => true,
        require => Package[httpd]
    }
}


