Dr. Watson script for Bro
=========================

Dr. Watson catcher script for Bro.

Overview
--------

Microsoft sends diagnostic information back to themselves through
a mechism named Dr. Watson.  The initial "StageOne" is unencrypted
and sent over HTTP so it's visible to Bro.  This script takes 
the StageOne messages and parses all available information out of
them to create a series of logs.

dr_watson_crash.log logs information whenever software crashes 
happen such as the application that crashed and why it crashed.

dr_watson_platform.log logs information about platforms discovered
from watson messages which could include information about the 
system manufacturer and model.

This script also feed information to the "Hardware" Bro script
that logs information about particular hardware discovered.

Installation
------------

::

	cd <prefix>/share/bro/site/
	git clone --recursive https://github.com/broala/bro-drwatson.git drwatson
	echo "@load drwatson" >> local.bro
