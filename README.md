check_mk-wmi
============

Provides a WMI agent for Check_MK. It consists of the check_mk-agent.wmi agent with plugins and checks for wmic_df and wmic_services.  The plugins assume that wmic is on the PATH. It can be downloaded here:

ftp://ftp.pbone.net/mirror/ftp.sourceforge.net/pub/sourceforge/p/pa/pandora/Tools%20and%20dependencies%20(All%20versions)/RPM%20CentOS,%20RHEL/wmic-4.0.0SVN-2.1.el5.centos.noarch.rpm

The individual agent and check files can be copied to the appropriate Check_MK directories in your install, or you can install using the packages/wmi-0.2.mkp package. 

A config might look like this:

    all_hosts = [
      'host1|wmi',
    ]

    datasource_programs = [
      ( "/usr/share/check_mk/agents/check_mk-agent.wmi &lt;HOST&gt; domain.com\\\\username password", [ 'wmi' ], ALL_HOSTS ),
    ]

*Notice that the "\" between the domain and the username must be escaped twice.

If you have any questions please email me at dlittle@toyatech.net.

Thanks and enjoy!
