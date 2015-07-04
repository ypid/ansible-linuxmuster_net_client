## linuxmuster_net-client-customize

[![Ansible Galaxy](http://img.shields.io/badge/galaxy-ypid.linuxmuster_net–client–customize-660198.svg?style=flat)](https://galaxy.ansible.com/list#/roles/4058)
[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)


Apply common customizations to a linuxmuster.net client.

See [linuxmuster.net](https://linuxmuster.net) for more information.

### Package list
The [package list](/vars/ypid_packages.yml) which is included in this role has been selected for a [Gymnasium](https://en.wikipedia.org/wiki/Gymnasium_%28school%29).
It includes many programs like:
*   Office: [LibreOffice](https://www.libreoffice.org/), [TeXLive](https://www.tug.org/texlive/)
*   Internet: [Firefox](https://www.mozilla.org/de/firefox/new/), [Thunderbird](https://www.mozilla.org/de/thunderbird/) (with [enigmail Plugin](https://www.thunderbird-mail.de/wiki/Enigmail_OpenPGP))
*   Education:
    * Mathematic: [kmplot](https://edu.kde.org/kmplot/), [geogebra](https://www.geogebra.org/), [jfractionlab](http://jfractionlab.sourceforge.net/), speedcrunch, kcalc, qalculate-gtk, tilem
    * Chemistry: [kalzium](https://edu.kde.org/kalzium/), gelemental, gperiodic
    * GIS: [josm](https://josm.openstreetmap.de/), [marble](https://marble.kde.org/), [viking](http://sourceforge.net/projects/viking/)
    * Astronomy: [stellarium](http://www.stellarium.org/), [celestia](http://www.shatters.net/celestia/), [gpredict](http://gpredict.oz9aec.net/)
    * Medical: [invesalius](http://www.cti.gov.br/invesalius/)
    * Language: [parley](https://edu.kde.org/applications/all/parley), [gnome-dictionary](https://wiki.gnome.org/Apps/Dictionary) (together with a local dict server for fast queries), [ktouch](https://edu.kde.org/applications/all/ktouch)
*   Media: [VLC](https://www.videolan.org/vlc/), [GIMP](http://www.gimp.org/), [Blender](https://www.blender.org/), [Clementine](https://www.clementine-player.org/), [Audacity](http://audacityteam.org/)
*   Software development:
    * Python
    * C/C++
    * Qt
    * HTML, JavaScript, CSS
    * SQL (MySQL Database Server with local Database for students)
    * Java/Android
    * Needed tools like [Vim](http://www.vim.org/), [emacs](https://www.gnu.org/software/emacs/), [git](https://git-scm.com/), [eclipse](https://eclipse.org/)
*   Networking: [Wireshark](https://www.wireshark.org/), [packeth](http://packeth.sourceforge.net/)

    Reasons: To learn how networks work. Students don’t have the permissions to actually sniff the network of course but there are [many dumps](https://wiki.wireshark.org/SampleCaptures) which can be analyzed.

The compressed image size is currently 7.2 GiB which is tiny compared to a Windows 7 image (with basically useful nothing in it).

### Installation

This role requires at least Ansible `v1.3`. To install it, run:

    ansible-galaxy install ypid.linuxmuster_net-client-customize

To install via git, run either:

    git clone https://github.com/ypid/ansible-linuxmuster_net-client-customize.git ypid.linuxmuster_net-client-customize
    git submodule add https://github.com/ypid/ansible-linuxmuster_net-client-customize.git roles/ypid.linuxmuster_net-client-customize




### Role variables

List of default variables available in the inventory:

    ---
    
    linuxmuster_net_client_customize_template_user: "linuxadmin"
    
    ## Work in progress: (((
    ## ToDo: Test on fresh system. Create user.
    # passwd localuser -d
    ## Local user name. Can also login, when the client is offline.
    linuxmuster_net_client_customize_local_user_name: "localuser"
    linuxmuster_net_client_customize_local_user_enable: False
    linuxmuster_net_client_customize_local_user_script_filepath: '/usr/local/bin/sync_localuser'
    
    ## Create the following directories for the local_user.
    linuxmuster_net_client_customize_local_user_directories:
      - "Dokumente_tmp"
    ## )))
    
    linuxmuster_net_client_customize_copy_custom_config_etc: True
    
    linuxmuster_net_client_customize_auto_shutdown_enable: True
    linuxmuster_net_client_customize_auto_shutdown_time:
      - hour: "17"
        minute: "15"
      - hour: "20"
      - hour: "00"
    
    ## Added paths here which should be synchronized to the target deleting all files not available on the source.
    linuxmuster_net_client_customize_etc_delete_sync:
      # - "/etc/linuxmuster-client/pre-mount.d"
      # - "/etc/linuxmuster-client/post-mount.d"
    
    
    ## If the following variable lists no packages, the default packages from vars/ypid_packages.yml
    ## will be installed.
    linuxmuster_net_client_apt_packages:
      # - "vim"
    
    ## Additional packages, configured in group and host scope.
    linuxmuster_net_client_apt_packages_group:
    linuxmuster_net_client_apt_packages_host:




### Authors and license

`linuxmuster_net-client-customize` role was written by:

- [Robin Schneider](https://github.com/ypid) | [e-mail](mailto:ypid@riseup.net)

License: [AGPLv3](https://tldrlegal.com/license/gnu-affero-general-public-license-v3-%28agpl-3.0%29)

***

README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).
