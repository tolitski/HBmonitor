

**HBMonitor no longer developing**

**Try to use more updated version by OA4DOA: https://github.com/yuvelq/FDMR-Monitor**


**HBmonitor is a "web dashboard" for HBlink by N0MJS.**

**New version of HBMonitor V2 (2021):**

https://github.com/sp2ong/HBMonv2


***This is version of HBMonitor V1 by SP2ONG 2019-2021***

I recommend not running HBmonitor on the same computer as HBlink3

HBmonitor tested on Debian v9 STRETCH

HBMonitor V1:
    cd /opt
    git clone https://github.com/sp2ong/HBmonitor.git
    cd HBmonitor
    
    If you want to try the HBMonitor version with BRIDGE status display on a separate page, 
    run the command below, if not skip this command:
    git checkout bridges
    
    chmod +x install.sh
    ./install.sh
    cp config-SAMPLE.py config.py
    edit config.py and change what you necessary
    cp utils/hbmon.service /lib/systemd/system/
    systemctl enable hbmon
    systemctl start hbmon
    systemctl status hbmon
    forward TCP ports 8080 and 9000 in firewall
    
    If you use openbrige links, in config.py in OPB_FILTER enter NETWORK_ID 
    to do not display unnecessary entries in LASTHEARD.
    
    Please remember the table lastherad displays only station transmissions that are longer than 2 seconds.
    
    If you don't want to have the lasherad list set in config.py :  
      LASTHEARD_INC = False
    
    If you want to have more than the last 10 entries in the Lastherad table
    change in the monitor.py file on line 629 https://github.com/sp2ong/HBmonitor/blob/master/monitor.py#L629
      if n == 10:
    for example:
      if n == 20:

    If you want to have access to HBmonitor via username and password, set it in config.py :
      WEB_AUTH =  True
    and set username and password in:    
      WEB_USER =  'hblink'
      WEB_PASS =  'hblink'

    If not need monitor online rules please use in config.py BRIDGES_INC = False

---

After update distribution of Linux jinja2 to version 3.x you can find problem with run HBMonitor with error:

     ValueError: The 'monitor' package was not installed in a way that PackageLoader understands.


You must uninstall jinja2 and reinstalling with this version Jinja2==2.11.3

    pip3 uninstall jinja2

and

    pip3 install Jinja2==2.11.3


---

**hbmonitor3 by KC1AWV**

Python 3 implementation of N0MJS HBmonitor for HBlink https://github.com/kc1awv/hbmonitor3 

---

Copyright (C) 2013-2018  Cortney T. Buffington, N0MJS <n0mjs@me.com>

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program; if not, write to the Free Software Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301  USA







