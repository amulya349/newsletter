Different branches of this repository
=====================================

master:  Reflects the current development branch where e.g. new
         newsletter versions are getting created in.

website: Contains the content, which is currently published on the
         webserver.

In order to bring something 'live' you have to choices:

1. Make usage of git cherry-pick <object> or
2. Merge complete branch master into website branch via e.g.
   git checkout website && git merge master


Prerequisites
=============

You will need some docutils installed, at least one of the following commands
should be present on your machine:

 rst2html
 rst2latex
 rst2pdf
 rst2odt


How to compile
==============

Compiling the newsletter is as simple as is couldn't be. Just define an
evironment variable named VOL and run make either wihtout parameters to
compile all, or with one of the parameters html, pdf, latex, odt to compile
just that file.

Examples:

 VOL=2 make                                  # compile all newsletters for vol_2
 VOL=2 make pdf                              # compile pdf from vol_2
 VOL=2 make html                             # compile html file for vol_2


How to release
==============

Things to do when releasing a new newsletter:

* tag the release
* merge the tag into branch website
* adjust the index.html link
* push that stuff and update it on the webserver
* check if http://newsletter.geany.org/ points to the new release
* check if http://newsletter.geany.org/newsletters.php lists everything correctly
* update the wiki page at https://wiki.geany.org/newsletter/start
* actually send out the newsletter to the mailing lists
