ansible-role-syncthing
======================

Install [syncthing](https://github.com/syncthing/syncthing) and [syncthing-inotify](https://github.com/syncthing/syncthing-inotify).

Since this is a highly personal role and includes things like checking for my [tinc](https://www.tinc-vpn.org) interface, it has only been tested
on Fedora and CentOS/RHEL systems. On those it should work well, though.

Requirements
------------

None.

Role Variables
--------------

Usually you should only need to change the following variables in `defaults/main.yml`:

    syncthing_user: azmo

Run syncthing as given user. Use systemd's service@user facilities to start syncthing@user and syncthing-inotify@user.

    syncthing_webguiport: 8384

Make syncthing listen on given port for its webui.

    syncthing_version: 0.13.10
    syncthing_inotify_version: 0.8.2

Pull and install given versions. Changing these triggers an install of new versions.

    syncthing_location: /usr/local/bin

Install binaries into given location.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
         - { role: azmodude.syncthing }

License
-------

BSD

Author Information
------------------

None.
