===============
Ansible Example
===============

This came about after a test for setting up ansible. So I can't claim that
any of this is the best way to do anything. Also the examples are very
Ubuntu/Debian specific, there are ways to make it more generic, but for my
purposes this isn't a huge priority.

Very specifically I was using clojure Leiningen install as the test for
configuration managers. The steps are basically:

- Download a file.
- Put it in a local location.
- Set it on your path.
- Then run the file.

Currently ansible has been the simplest to run these steps.

-------
Running
-------

Install:

- VirtualBox
- Vagrant
- Ansible

By default it will run the website.yml file. Change the "ansible.playbook"
setting in the Vagrant file to change that. Only clojure.yml is currently
supported, but it's not that hard to add more.

Go to the main directory and run::

    vagrant up

----
TODO
----

- See about passing variables into the vagrant file. For roles if nothing
  else.
- See if the guard variables can be removed in the case of updates.
- Update the vim section to handle other potential package managers.
- The npm part could be spit, it does both the npm install (which is probably
  better done through package managers) and it sets things up to not require
  sudo for global packages.
- The elsatic search taks uses a hard-coded version.
- Move the become statements higher so that they don't have to be littered
  everywhere else.
- The postgresql section was originally written for CentOS. The steps aren't
  all necessary for Ubuntu. It would be nice to test that further and make
  that and the other scripts even more generic.
