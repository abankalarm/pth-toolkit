### Since the out of box version of pth toolkit has actually got pretty old here are the newer steps to make it run - that i had piece together myself and still run in 2021

## Changes:
I have added/replaced several static libraries that aren't shipped anymore with newer releases or dont run properly in the newer distos(e.g. libgnutls.so.26, libreadline.so.6) so you are really good to go now ;)
I have also added the steps below without which you will keep running into errors

## Steps:
1. Binaries only run when placed in /opt/pth due to compile time hardcoded paths.
2. export path using export PATH="/opt/pth/bin:$PATH"

## Tested on
kernel - 5.11.0-7614-generic
Ubuntu - 20.10
x86_64

## Still facing issues?
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
(not super sure how helpful this was in making them run but was one of the commands that i did run)

Feel free to create one in issue tabs

# ORIGINAL DESCRIPTION
pth-toolkit
===========

A modified version of the passing-the-hash tool collection https://code.google.com/p/passing-the-hash/ designed to be portable and work straight out of the box even on the most 'bare bones' systems

The master branch is compiled for amd64, the final goal will be to cross compile these tools to every possible architecture 

Currently this repo provides the following patched tools/utilities:
================================================
- winexe
- wmic 
- wmis
- rpcclient
- smbclient
- smbget
- net

Requirements
============

- ```sh``` 


All tools were tested on a bare bones Arch linux install with only the `base` package.  


When would this be useful?
=========================
- When your rocking a custom pentesting OS and you don't want to go through the agony of compiling and patching these tools yourself
- For post-exploitation to pivot to a Windows box/domain from a compromised *nix host! Just clone this repo or download the tarball and your ready to pass all the hashes!


