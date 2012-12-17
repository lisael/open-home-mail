====================
Software Achitecture
====================

Introduction
============

To be able to send and recieve mails, 3 parts are needed:

- The piece of software to read and write mails

- The piece of software to send mails

- The piece of software to recieve mails.

The mail reader
===============

For the first iteration of the project, the mail reader is beyond
scope. It is always possible to read and write mail via another piece
of software like thunderbird or evolution for example.

The Next itteration will give access to a webmail like Roundcube.

The Mail Sender
===============

For his high stability, easy configuration and memory fooprint, the
mail sender should be : Postfix

The Mail Receiver
=================

For the same reasons, than the Mail sender, my choice will be Courier.

Maildirectory and user configuration
====================================

Things should remain as simple as possible. For this reason, each new
mail will be created as a unix user :

- home/user/Maildir

- user@domain.com

Passwords and other authentication stuff will be done by PAM. The
prinicipal reason beyon simplicity is to be future proof. In some next
releases of other features like PhotoGallery, it will be more
manageable to have a home for each user.

In Next release, it will be possible to let a user create some alias
and other mailbox but for now 1 email == 1 unix user.

RoadMap
=======

Version 0.2: bootstrap
----------------------

Manual installation of the complete mail system on the Raspberry
Pi. This version will be only a tutorial. It will help us find the
main problems, the configuration option and choices we have and so on.

In this version the user must have a domain to bind mail to. He must
manually open the needed ports on his Internet Box.

Version 0.4: automation
-----------------------

We should now write the scripts to easyliy configure the complete
system with what we have learn from version 0.1

The user need a domain ans must manually open the ports on his
internet box.

A main script has to be launched to install the complete
system and (Postfix + Courier)

Another script has to be launched to create a new email address.

Those scripts must be launched as root.

Version 0.6: Web configuration
------------------------------

Now we must develop a simple web application to create the complete
system and let users create their email boxes.

When the user plug the raspberry in the internet box, the raspberry must
be reachable in the local network (avahi ? something else ?)

Domain and Port forwarding must be set manualy

Version 0.8: Home Mail Subdomain and auto-DNS
---------------------------------------------

In this version, the main server (aka: Home Mail) must be able to
redirect subdomains to configured machines. The need of a personal
domain is no more mandatory. We must be clever because a lot of box
are dynamic IP so the main server must be able to update his bind
configuration via scripting or API.

Openning of ports on the internet boxes are always mandatory.

Version 1.0 : The Webmail
-------------------------

In this version we also configure a webmail. So a user able to forward
port on his internet box is 1 step away of freed himself from the
internet giants. He just have to select a subdomain, create some
emails and he is ready to go to send and receive mails for and to his
raspberry box.

Version 1.2: Auto-Port Forwarding
---------------------------------

We should have a way to automaticaly forward port from the internet
boxes to the raspberry.
