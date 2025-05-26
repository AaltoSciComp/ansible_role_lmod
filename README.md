ansible_role_lmod
=================

This role installs and configures Lmod.

Requirements
------------

None.

Role Variables
--------------

| Variable name               | Default value                              | Description                                                                                          |
|-----------------------------|--------------------------------------------|------------------------------------------------------------------------------------------------------|
| `lmod_install`              | `true`                                     | Whether role should install Lmod.                                                                    |
| `lmod_modulepaths`          | `["/usr/share/lmod/lmod/modulefiles/Core"]`| Paths to include in the `LMOD_MODULEPATH_INIT`-file                                                  |
| `lmod_modulepaths_path`     | `""`                                       | Location to the `LMOD_MODULEPATH_INIT` file. If empty, default `/etc/lmod/.modulespath` will be used |
| `lmod_sitepackage_template` | `"files/SitePackage.lua.j2"`               | Template for the SitePackage.lua-file. If empty, file won't be templated.                            |
| `lmod_sitepackage_dir`      | `"/etc/lmod/"`                             | Directory where SitePackage.lua should be.                                                           |
| `lmod_admin_file_template`  | `"files/admin.list.j2"`                    | Template for the admin.list-file. If empty, file won't be templated.                                 |
| `lmod_admin_file_path`      | `"/etc/lmod/admin.list`                    | Path where admin.list should be.                                                                     |
| `lmod_modulerc_template`    | `"files/modulerc.lua.j2"`                  | Template for the modulerc.lua-file. If empty, file won't be templated.                               |
| `lmod_modulerc_path`        | `"/etc/lmod/modulerc.lua"`                 | Path where modulerc.lua should be.                                                                   |
| `lmod_extra_env_vars`       | `{}`                                       | Dictionary of extra environment variables that should be specified in the init scripts.              |
| `lmod_norootmodpath`        | `false`                                    | Disable lmod path setting for root via LMOD_MODULEPATH_INIT                                          |
| `lmod_default_modules`      | `[]`                                       | List of modules that will be loaded by default                                                       |

Dependencies
------------

None.

Example Playbook
----------------

```yml
- hosts: servers
  roles:
    - role: ansible_role_lmod
      vars:
        lmod_modulepaths:
          - /appl/software/modules
```

License
-------

MIT

Author Information
------------------

Simo Tuomisto, Aalto University 2024
