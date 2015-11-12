Phantomjs
=========


Overview
--------

Role to install PhantomJS or to build it from source, or both.

Installation
------------

```
ansible-galaxy install marconius.phantomjs
```

Variables
---------

`defaults/main.yml` Contains general PhantomJS parameters

```yaml
phantomjs_enabled_on_startup: true
phantomjs_git_repository: https://github.com/ariya/phantomjs.git
```

`vars/main.yml` Contains machine-specific parameters general to all platforms

```yaml
phantomjs_build_from_source: no
phantomjs_binary_install: no
phantomjs_build_job_count: "{{ ansible_processor_cores }}"
```

`vars/Debian.yml` Contains machine-and-Debian-specific parameters



Examples
--------

A "vanilla" install of the OS-provided PhantomJS

```yaml
---
- hosts: all
  roles:
    - role: marconius.phantomjs
      become: yes
```

An installation of PhantomJS from included binary file
```yaml
---
- hosts: all
  roles:
    - role: marconius.phantomjs
      phantomjs_binary_install: yes
      become: yes
```

Just build PhantomJS from official repo
```yaml
---
- hosts: all
  roles:
    - role: marconius.phantomjs
      phantomjs_build_from_source: yes
      become: yes
```

Build PhantomJS binary from source and install that build
```yaml
---
- hosts: all
  roles:
    - role: marconius.phantomjs
      phantomjs_binary_install: yes
      phantomjs_build_from_source: yes
      become: yes
```

License
-------

MIT


Author Information
------------------

marconius <notification@marco.link>

