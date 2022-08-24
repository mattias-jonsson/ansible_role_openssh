Ansible Role: ansible_role_openssh
=========

Installs and configures openssh server/client on the following Linux distributions:

<ul>
<li>CentOS 7
<li>Red Hat Enterprise Linux 7
<li>Ubuntu 18/20/22
</ul>

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see `defaults/main.yml`):

    ansible_role_openssh_sshd_acceptenv:

    ansible_role_openssh_sshd_addressfamily:

    ansible_role_openssh_sshd_allowagentforwarding:

    ansible_role_openssh_sshd_allowtcpforwarding:

    ansible_role_openssh_sshd_authorizedkeyscommand:

    ansible_role_openssh_sshd_authorizedkeyscommanduser:

    ansible_role_openssh_sshd_authorizedkeysfile:

    ansible_role_openssh_sshd_authorizedprincipalsfile:

    ansible_role_openssh_sshd_banner:

    ansible_role_openssh_sshd_challengeresponseauthentication:

    ansible_role_openssh_sshd_chrootdirectory:

    ansible_role_openssh_sshd_clientalivecountmax:
    
    ansible_role_openssh_sshd_clientaliveinterval:

    ansible_role_openssh_sshd_compression:

    ansible_role_openssh_sshd_gatewayports:

    ansible_role_openssh_sshd_gssapiauthentication:

    ansible_role_openssh_sshd_gssapicleanupcredentials:

    ansible_role_openssh_sshd_gssapienablek5users:

    ansible_role_openssh_sshd_gssapikeyexchange:

    ansible_role_openssh_sshd_gssapistrictacceptorcheck:

    ansible_role_openssh_sshd_hostbasedauthentication:

    ansible_role_openssh_sshd_hostkey:

    ansible_role_openssh_sshd_ignorerhosts:

    ansible_role_openssh_sshd_ignoreuserknownhosts:

    ansible_role_openssh_sshd_kbdinteractiveauthentication:

    ansible_role_openssh_sshd_kerberosauthentication:

    ansible_role_openssh_sshd_kerberosgetafstoken:

    ansible_role_openssh_sshd_kerberosorlocalpasswd:

    ansible_role_openssh_sshd_kerberosticketcleanup:

    ansible_role_openssh_sshd_kerberosusekuserok:

    ansible_role_openssh_sshd_listenaddress:

    ansible_role_openssh_sshd_logingracetime:

    ansible_role_openssh_sshd_loglevel:

    ansible_role_openssh_sshd_maxauthtries:

    ansible_role_openssh_sshd_maxsessions:

    ansible_role_openssh_sshd_maxstartups:

    ansible_role_openssh_sshd_passwordauthentication:

    ansible_role_openssh_sshd_permitemptypasswords:

    ansible_role_openssh_sshd_permitrootlogin:

    ansible_role_openssh_sshd_permittty:

    ansible_role_openssh_sshd_permittunnel:

    ansible_role_openssh_sshd_permituserenvironment:

    ansible_role_openssh_sshd_pidfile:

    ansible_role_openssh_sshd_port:

    ansible_role_openssh_sshd_printlastlog:

    ansible_role_openssh_sshd_printmotd:

    ansible_role_openssh_sshd_pubkeyauthentication:

    ansible_role_openssh_sshd_rekeylimit:

    ansible_role_openssh_sshd_showpatchlevel:

    ansible_role_openssh_sshd_strictmodes:

    ansible_role_openssh_sshd_subsystem:

    ansible_role_openssh_sshd_syslogfacility:

    ansible_role_openssh_sshd_tcpkeepalive:

    ansible_role_openssh_sshd_usedns:

    ansible_role_openssh_sshd_uselogin:

    ansible_role_openssh_sshd_usepam:

    ansible_role_openssh_sshd_useprivilegeseparation:

    ansible_role_openssh_sshd_versionaddendum:

    ansible_role_openssh_sshd_x11displayoffset:

    ansible_role_openssh_sshd_x11forwarding:

    ansible_role_openssh_sshd_x11uselocalhost:


Available keywords for `ansible_role_openssh_sshd_match_statements` are among the following but may differ dependeing on distribution. Please ensure to use lowercase when specifying the keywords:

`acceptenv`, `allowagentforwarding`, `allowgroups`, `allowstreamlocalforwarding`, `allowtcpforwarding`, `allowusers`, `authenticationmethods`, `authorizedkeyscommand`, `authorizedkeyscommanduser`, `authorizedkeysfile`, `authorizedprincipalscommand`, `authorizedprincipalscommanduser`, `authorizedprincipalsfile`, `banner`, `casignaturealgorithms`, `chrootdirectory`, `clientalivecountmax`, `clientaliveinterval`, `denygroups`, `denyusers`, `disableforwarding`, `exposeauthinfo`, `forcecommand`, `gssapiauthentication`, `gatewayports`, `hostbasedacceptedalgorithms`, `hostbasedacceptedkeytypes`, `hostbasedauthentication`, `hostbasedusesnamefrompacketonly`, `ipqos`, `ignorerhosts`, `include`, `kbdinteractiveauthentication`, `kerberosauthentication`, `loglevel`, `maxauthtries`, `maxsessions`, `passwordauthentication`, `permitemptypasswords`, `permitlisten`, `permitopen`, `permitrootlogin`, `permittty`, `permittunnel`, `permituserrc`, `pubkeyacceptedalgorithms`, `pubkeyacceptedkeytypes`, `pubkeyauthoptions`, `pubkeyauthentication`, `rdomain`, `rekeylimit`, `revokedkeys`, `setenv`, `streamlocalbindmask`, `streamlocalbindunlink`, `trustedusercakeys`, `x11displayoffset`, `x11forwarding`, `x11uselocalhost`, `x11uselocalhost`


Dependencies
------------

None.

Example Playbook
----------------


    - hosts: servers

      vars:

        ansible_role_openssh_sshd_listenaddress: 
          - '192.168.0.1'
        ansible_role_openssh_sshd_port:
          - '22'
        ansible_role_openssh_sshd_logingracetime: '1m'
        ansible_role_openssh_sshd_maxauthtries: '3'
        ansible_role_openssh_sshd_maxsessions: '1'
        ansible_role_openssh_sshd_authorizedkeyscommand: '/usr/bin/sss_ssh_authorizedkeys'
        ansible_role_openssh_sshd_authorizedkeyscommanduser: 'root'
        ansible_role_openssh_sshd_match_statements:
        - type: user
          name: someuser
          options:
            chrootdirectory: '%h'
            forcecommand: 'internal-sftp'
            allowtcpforwarding: 'no'
            x11forwarding: 'no'

      roles:
         - role: ansible_role_openssh

License
-------

MIT

Author Information
------------------

Mattias Jonsson