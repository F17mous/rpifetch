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

# .SH DESCRIPTION
This handy Bash script can be used to generate one of those
nifty terminal theme information + ASCII distribution logos you
see in everyone's screenshots nowadays. It will auto-detect your
distribution and display an ASCII version of that distribution's
logo and some valuable information to the right. There are options
to specify no ASCII art, colors, taking a screenshot upon displaying
info, and even customizing the screenshot command!
This script is very easy to add to and can easily be extended.
.PP
Supported GNU/Linux Distributions:
.IP
.\" @supported_distros_start@
Alpine Linux, Antergos, Arch Linux (Old and Current Logos), BLAG, BunsenLabs, CentOS, Chakra, Chapeau, Chrome OS, Chromium OS, CrunchBang, CRUX, Debian, Deepin, Devuan, Dragora, elementary OS, Evolve OS, Exherbo, Fedora, Frugalware, Fuduntu, Funtoo, Fux, Gentoo, gNewSense, Jiyuu Linux, Kali Linux, KaOS, KDE neon, Kogaion, Korora, LinuxDeepin, Linux Mint, LMDE, Logos, Mageia, Mandriva/Mandrake, Manjaro, Mer, Netrunner, NixOS, openSUSE, Oracle Linux, Parabola GNU/Linux-libre, Pardus, PCLinuxOS, PeppermintOS, Qubes OS, Raspbian, Red Hat Enterprise Linux, ROSA, Sabayon, SailfishOS, Scientific Linux, Slackware, Solus, SparkyLinux, SteamOS, SUSE Linux Enterprise, SwagArch, TinyCore, Trisquel, Ubuntu, Viperr and Void.
.\" @supported_distros_end@
.PP
Other Supported Systems:
.IP
.\" @supported_other_start@
Dragonfly/Free/Open/Net BSD, Haiku, Mac OS X, Windows+Cygwin and Windows+MSYS2.
.\" @supported_other_end@
.PP
Supported Desktop Managers:
.IP
.\" @supported_dms_start@
KDE, GNOME, Unity, Xfce, LXDE, Cinnamon, MATE, Deepin, CDE, RazorQt and Trinity.
.\" @supported_dms_end@
.PP
Supported Window Managers:
.IP
.\" @supported_wms_start@
2bwm, 9wm, Awesome, Beryl, Blackbox, Cinnamon, chromeos-wm, Compiz, deepin-wm, dminiwm, dwm, dtwm, E16, E17, echinus, Emerald, FluxBox, FLWM, FVWM, herbstluftwm, howm, IceWM, KWin, Metacity, monsterwm, Musca, Gala, Mutter, Muffin, Notion, OpenBox, PekWM, Ratpoison, Sawfish, ScrotWM, SpectrWM, StumpWM, subtle, sway, TWin, WindowMaker, WMFS, wmii, Xfwm4, XMonad and i3.
.\" @supported_wms_end@

.SH OPTIONS
.TP
.B \-v
Verbose output.
.TP
.B \-o 'OPTIONS'
Allows for setting script variables on the
command line. Must be in the following format:
\&'OPTION1="OPTIONARG1";OPTION2="OPTIONARG2"'
.TP
.B -d '+var;-var;var'
Allows for setting what information is displayed on the command line. You can
add displays with +var,var.  You can delete displays with -var,var. Setting
without + or - will set display to that explicit combination. Add and delete
statements may be used in conjunction by placing a ; between them as so:
+var,var,var;-var,var.
.TP
.B \-n
Do not display ASCII distribution logo.
.TP
.B \-L
Display ASCII distribution logo only.
.TP
.B \-N
Strip all color from output.
.TP
.B \-w
Wrap long lines.
.TP
.B \-t
Truncate output based on terminal width (Experimental!).
.TP
.B \-p
Output in portrait mode, with logo above info.
.TP
.B \-s [-u IMGHOST]
Using this flag tells the script that you want it
to take a screenshot. Use the \fB\-u\fR flag if you would like
to upload the screenshots to one of the pre-configured
locations. These include: teknik, imgur, mediacrush and hmp.
.TP
.B \-c string
You may change the outputted colors with \fB\-c\fR. The format is
as follows: [0\-9][0\-9],[0\-9][0\-9]. The first argument controls the
ASCII logo colors and the label colors. The second argument
controls the colors of the information found. One argument may be
used without the other.
.TP
.B \-a 'PATH'
You can specify a custom ASCII art by passing the path to a Bash script,
defining \fBstartline\fR and \fBfulloutput\fR variables, and optionally
\fBlabelcolor\fR and \fBtextcolor\fR. See the \fBasciiText\fR function
in the source code for more informations on the variables format.
.TP
.B \-S 'COMMAND'
Here you can specify a custom screenshot command for
the script to execute. Surrounding quotes are required.
.TP
.B \-D 'DISTRO'
Here you can specify your distribution for the script
to use. Surrounding quotes are required.
.TP
.B \-A 'DISTRO'
Here you can specify the distribution art that you want
displayed. This is for when you want your distro
detected but want to display a different logo.
.TP
.B \-E
Suppress output of errors.
.TP
.B \-V, \-\-version
Display current script version.
.TP
.B \-h, \-\-help
Display this help.
