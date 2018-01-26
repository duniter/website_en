# Prerequisites to build the windows version of duniter

To produce a Windows Release file of duniter, there are a couple of prerequisites:

- at least 30 Gb of free disk space as the virtualbox image is 13 Gb and is then duplicated,
- 8 Gb of memory is a good start, 4 is really low but doable.
- vagrant, a recent version since older versions may not be compatible with virtualbox, typically a 2.0.0. If you're on Ubuntu 14 as I am, the repo is not up-to-date, you'll have to grab the vagrant install there: https://www.vagrantup.com/downloads.html
- virtualbox, preferably a recent version (currently 5.2 - again, on Ubuntu 14, you'll have to install the .deb from https://www.virtualbox.org/wiki/Linux_Downloads ). If you have already done a release before, make sure that the corresponding virtual machine is not present in the list of virtual machines. If it is, delete it, otherwise the release will fail because it won't want to overwrite it.
- git,
- node (preferably the current version used by duniter, right now it is 8.9.1).

# Pulling from git and building

Then just do the following (and adapt to the current branch, if changed):

>git clone https://git.duniter.org/nodes/typescript/duniter.git -b 1.6
cd duniter/

If you are low in memory (less than 4 Gb **available**), you can open the file release/arch/windows/Vagrantfile, look for "vb.memory" and set it to some lower value (I would recommend at least 2048).
Then run:

>release/scripts/build.sh make win v<version_number>

Let the release do its work. The first time, Vagrant will need to download the virtualbox image (13 Gb) so depending on your Internet connection it might be long, but it will reuse it the next times (on ubuntu it is stored in <home>/.vagrant.d/boxes, make sure you have some disk space there).

If you have a Vagrant error message such as "No usable default provider could be found for your system.", then your vagrant version is incompatible with your VirtualBox version, and it means Vagrant cannot work with VirtualBox: you have to upgrade Vagrant to a newer version.

# Uploading the release on gitlab

Once the release is done, the .exe file is in release/arch/win.

Go to https://git.duniter.org/nodes/typescript/duniter/tags/

Edit the release notes page of the wanted tag and upload the .exe file there, try to respect the format of existing packages on the page.

To do some cleanup, you can simply delete the virtual machine that was created (and yes you can delete all files for it when VB asks), and even delete the duniter directory in which you produced the release to free up some disk space.

You're done!
