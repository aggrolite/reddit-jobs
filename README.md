# reddit-jobs
Receive e-mail notifying new jobs at Reddit.

# Description
This is a script I wrote in Python which sends a notification via email when Reddit has posted new jobs at [jobs.level.com/reddit](https://jobs.lever.co/reddit). This script is intended to be run as a daily cron job.

Running the script for the first time will produce the following effects:

* all jobs found by the script are considered new
* "new" jobs found are then cached in memory
* "new" jobs are sent off to the e-mail address specified by option `--email`.

Thereafter, the script will continue to scrape all jobs posted, but decide which jobs are "new" based on which jobs have already been cached.

# Dependencies
* Python 3
* memcached server running on localhost
* The following Python libraries: pylibmc, logging, smtplib, urllib, bs4, pprint, optparse

# Note
Please note that I am using lxml's HTML parser. This parser is apparently very fast, but it does have an external C dependency. Make sure you have that dependency. See lxml's [requirements](http://lxml.de/installation.html#requirements) page for more details.

# TODO
* Detect an empty jobs listing page
* Allow user to set logging level
