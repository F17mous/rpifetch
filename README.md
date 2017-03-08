# rpifetch
# What is RPIfetch ?
rpiFetch is a "Bash Screenshot Information Tool". This handy Bash script can be used to generate one of those nifty terminal theme information + ASCII distribution logos you see in everyone's screenshots nowadays. It will auto-detect your distribution and display an ASCII version of that distribution's logo and some valuable information to the right. There are options to specify no ascii art, colors, taking a screenshot upon displaying info, and even customizing the screenshot command! This script is very easy to add to and can easily be extended.

# How does it look?:
this one is from my "raspberry pi 3 b model"

                          ./+o+-       f17mous@chetouane
                  yyyyy- -yyyyyy+      OS: Ubuntu 16.04 xenial
               ://+//////-yyyyyyo      Kernel: armv7l Linux 4.1.19-v7+
           .++ .:/++++++/-.+sss/`      Uptime: 3m
         .:++o:  /++++++++/:--:/-      Packages: 1949
        o:+o+:++.`..```.-/oo+++++/     Shell: 1963
       .:+o:+o/.          `+sssoo+/    CPU: ARMv7 rev 4 (v7l) @ 4x 1.2GHz
  .++/+:+oo+o:`             /sssooo.   RAM: 232MiB / 925MiB
 /+++//+:`oo+o               /::--:.
 \+/+o+++`o++o               ++////.
  .++.o+++oo+:`             /dddhhh.
       .+.o+oo:.          `oddhhhh+
        \+.++o+o``-````.:ohdhhhhh+
         `:o+++ `ohhhhhhhhyo++os:
           .o:`.syhhhhhhh/.oo++o`
               /osyyyyyyo++ooo+++/
                   ````` +oo+++o\:
                          `oo++.
.
# Download
https://github.com/F17mous/rpiFetch

# installation:
cd /tmp
git clone git://github.com/F17mous/rpifetch.git rpifetch

sudo cp rpifetch/rpifetch-dev /usr/bin/rpifetch
sudo chmod 755 /usr/bin/rpifetch

# Test it:
rpifetch

if it works, add it to your shell

# Edit either ~/.bashrc or ~/.zshrc, depends on which shell you use and add the following at the bottom:
if [ -f /usr/bin/rpifetch ]; then rpifetch; fi
