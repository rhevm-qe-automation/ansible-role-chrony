# ericsysmin.chrony

This role enables users to install and configure chrony on their hosts.

## Build Status

[![Build Status](https://travis-ci.org/ericsysmin/ansible-role-chrony.svg?branch=master)](https://travis-ci.org/ericsysmin/ansible-role-chrony)

## Requirements

None

## Role Variables

| Variable | Required | Default | Comments |
|----------|----------|---------|----------|
| `chrony_pkg_state` | No | `present` | Set pkg `enabled`, `disabled`, `latest`  |
| `chrony_service_state` | No | `started` | Set service state, started, enabled or disabled  |
| `chrony_service_enabled` | No | `yes` | A list of NTP servers to use.  |
| `chrony_config_server` | No | `["0.pool.ntp.org","1.pool.ntp.org","2.pool.ntp.org", "3.pool.ntp.org"]`` | A list of NTP servers to use.  |
| `chrony_config_logdir` | No | `/var/log/chrony` | A list of NTP servers to use.  |

## Examples

1) Install chrony and use the default settings.

```

- hosts: all
  roles:
    - role: ericsysmin.chrony
```

2) Install chrony and use custom servers.

```

- hosts: all
  roles:
    - role: ericsysmin.chrony
      chrony_config_server:
				- 0.pool.ntp.org
				- 2.pool.ntp.org
```

## License

Apache 2.0

## Author Information

[ericsysmin](https://ericsysmin.com)
