===============
Ansible Example
===============

This came about after a test for setting up ansible. So I can't claim that
any of this is the best way to do anything. Also the examples are very
Ubuntu/Debian specific, I suspect there are ways to make it more generic,
but for my purposes this isn't a huge priority.

Very specifically I was using clojure Leiningen install as the test for
configuration managers. The steps are basically: download a file, put it
in a local location, set it on your path, and then run the file. Currently
ansible has been the simplest to run these steps.

-------
Running
-------

Install:

- VirtualBox
- Vagrant
- Ansible

If there are any taks you don't want, comment them out (#) in the
playbook.yml.

Go to the main directory and run::

    vagrant up

----
TODO
----

- See about removing the guard variables. If for no other reason this will
  fail if you try to update a newer version because the check will say it
  already exists.
- The download was attempting to re-download everything even if the file
  already existed, that's why the guard variables exist.
- The vim section tries to grab a local vimrc, which may require other setup
  for package managers (like Vundle, NeoBundle, etc.) Add that in.
- The npm part could be spit, it does both the npm install (which is probably
  better done through package managers) and it sets things up to not require
  sudo for global packages.
- Despite being the first thing written (well, because of it actually), lein
  actually doesn't even attempt guard conditions, which could use some updates.
