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
      ( "/usr/share/check_mk/agents/check_mk-agent.wmi <HOST> domain.com\\\\username password", [ 'wmi' ], ALL_HOSTS ),
    ]

    inventory_services = [
      "~OracleService running",
    ]

*Notice that the "\" between the domain and the username must be escaped twice.
*Both plugins are written to the same output spec as the existing df and services checks. This means that all configuration options for these checks are identical to the ones distributed with check_mk. You can read more about the options available for the df check here:
http://mathias-kettner.de/checkmk_check_df.html
and the services check here:
http://mathias-kettner.de/checkmk_check_services.html  

If you have any questions please email me at dlittle@toyatech.net.

Thanks and enjoy!
