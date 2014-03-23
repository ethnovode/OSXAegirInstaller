OSXAegirInstaller
=================

This script does everything that you need for Aegir to run natively on your Mac, it has been recently tested Mavericks 10.9, 10.9.1, 10.9.2. I expect it will work fine on 10.8.x as well but am not really supporting legacy versions of OS X anymore.

It took around 3 months hacking and a patch to the Aegir project to get Aegir installable on a mac and then approximately 2 weeks to write the initial version of this script so I hope you say thanks with a [Paypal Donation](https://www.paypal.com/webscr?cmd=_donations&business=brian@briangilbert.net&item_name=OSXAegir%20Donation&currency_code=AUD) for the time I've saved you.

Prerequisites
-----------------
*A gmail address/password you can use for relaying emails
*XCode if you aren't using 10.9+

What get's installed?
---------------------------
This script installs/configures everything you need for Aegir to work on OSX, mostly via Homebrew:
* wget
* gzip
* drush 6
* dnsmasq
* nginx (with geoip and uploadprogress)
* mariadb
* php 5.3/5.4/5.5 (with uploadprogress, xhprof and xdebug)
* postfix (relaying email via a gmail account you own)
* solr4 (optional)

And then installs Aegir 6.x-2.0 stable

Once installed you can access the Aegir dashboard at [http://aegir.ld](http://aegir.ld)
Any site you create should ends in .ld or have an alias ending in .ld so that it will resolve to localhost and work within your browser.

The script creates unsigned SSL certificates so that you can access any of the sites you create using https.

Installation Instructions
------------------------------
Execute the following in terminal to run the installer:

    cd ~
    curl -O https://raw.github.com/BrianGilbert/OSXAegirInstaller/master/aegir.sh
    chmod +x aegir.sh
    ./aegir.sh

Post Install
---------------
After installation change php versions (and restart nginx) by running the following commands:

    go53
    go54
    go54

Uninstall
-----------
If the install fails or you don't like Aegir, you can re-run the script to uninstall everything.

Warning
-----------
I have tested this script extensivley on a clean install of OSX, but I take no responsability for anything that happens to your computer using the script.
I'd recommend you use Disk Utility to repair permissions on your primary drive before running this script. 

It should be fine to install on any machine that doesn't have a webserver already running on port 80 or a DB server already running on 3306, this means that you can have MAMP or Acquia Dev Desktop installed as well as Aegir (unless you have changed the default ports on either of these to 80/3306).

Any improvements gladly accepted as pull requests!

Donations
-------------
It took around 3 months hacking and a patch to the Aegir project to get Aegir installable on a mac and then approximately 2 weeks to write the initial version of this script so I hope you say thanks with a [Paypal Donation](https://www.paypal.com/webscr?cmd=_donations&business=brian@briangilbert.net&item_name=OSXAegir%20Donation&currency_code=AUD) for the time I've saved you.

