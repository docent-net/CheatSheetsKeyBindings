systemd cheat-sheet:
  - urls:
    - http://www.freedesktop.org/software/systemd/man/
    - https://fedoraproject.org/wiki/Systemd
    - http://0pointer.de/blog/projects/systemd-docs.html
  - managing services:
    - systemctl - list running services
    - systemctl status some-service - show runtime status of service
    - systemd-cgls - show cgroup tree
    - systemctl start/stop/restart/status/enable/disable/is-enabled someservice
  - managing targets (runlevels):
    - systemctl get-default - what is the default target (runlevel)?
    - change boot target (runlevel):
      - ln -sf /usr/lib/systemd/system/multi-user.target /etc/systemd/system/default.target (like runlevel 3)
      - ln -sf /usr/lib/systemd/system/graphical.target /etc/systemd/system/default.target (like runlevel 5)
      - systemctl isolate graphical.target - change current target (runlevel); no
        effect after reboot
    - systemctl list-units --type=target - what is the current target (runlevel)?
    - systemctl show -p "Wants" multi-user.target - show target's dependencies 
      (could also try with "WantedBy", "Requires", "RequiredBy", "Conflicts", 
      "ConflictedBy", "Before", "After")
  - systemd --test --system --unit=foobar.target - check what would get started
    after booting into specific boot target
  - alias psc='ps xawf -eo pid,user,cgroup,args' - alias for ps with cgroups

