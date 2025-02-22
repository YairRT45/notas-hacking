How to automate tasks to run at intervals on linux servers?
Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 60916
Username: picoplayer 
Password: kZx-HVJKu8
```

Hints:
1. None

## Solución 1:
Revisamos el archivo crontab:
```
picoplayer@challenge:/$ cd etc/
picoplayer@challenge:/etc$ ls
adduser.conf            debconf.conf    hostname       logrotate.d          pam.conf   resolv.conf  sysctl.conf
alternatives            debian_version  hosts          lsb-release          pam.d      rmt          sysctl.d
apt                     default         hosts.allow    machine-id           passwd     security     systemd
bash.bashrc             deluser.conf    hosts.deny     magic                passwd-    selinux      terminfo
bindresvport.blacklist  dhcp            init.d         magic.mime           profile    shadow       timezone
binfmt.d                dpkg            inputrc        mailcap              profile.d  shadow-      tmpfiles.d
ca-certificates         e2scrub.conf    issue          mailcap.order        python3    shells       ucf.conf
ca-certificates.conf    environment     issue.net      mime.types           python3.8  skel         ufw
cloud                   fstab           kernel         mke2fs.conf          rc0.d      ssh          update-motd.d
cron.d                  gai.conf        ld.so.cache    modules-load.d       rc1.d      ssl          wgetrc
cron.daily              group           ld.so.conf     mtab                 rc2.d      subgid       xattr.conf
cron.hourly             group-          ld.so.conf.d   networkd-dispatcher  rc3.d      subgid-      xdg
cron.monthly            gshadow         legal          networks             rc4.d      subuid
cron.weekly             gshadow-        libaudit.conf  nsswitch.conf        rc5.d      subuid-
crontab                 gss             localtime      opt                  rc6.d      sudoers
dbus-1                  host.conf       login.defs     os-release           rcS.d      sudoers.d
picoplayer@challenge:/etc$ cat crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}
```