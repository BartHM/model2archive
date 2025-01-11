# New XENIX Files
| File            |        Size | Description        |
|:----------------|------------:|:-------------------|
| Tandy_68000_XENIX_3.4.3-FINAL_2023-05-06.zip | 330,753 | Upgrade disk image for upgrading XENIX 3.3 to XENIX 3.4.<br/><i>Yes, that's right, it's a new version of XENIX!</i>  Read the included Tandy_68000_XENIX_3.4.3_Release_Notes.txt file for full information about what's included in this release.<br/><br/>Here is a short summary from the Release Notes:<br/>New Kernel Features<br/><ul><li>Brand new kernel supporting automatic detection of MMU size, with automatic adjusting of user memory to fit what the MMU can support.</li><li>New crashbeep feature, which is settable using /etc/cfg.  The kernel will beep when halting for any reason.</li><li>Automatic move of allocateable items (such as disk buffers) outside of MMU-addressable space, which maximizes memory for user processes.  This is applicable for systems with no MMU exension board and more than 1MB of memory, and for systems with a Tandy MMU exension board (or clone) and more than 4MB of memory.</li><li>New Real Time Clock driver for both trs80gp (use the '-ee' option) and Tandy Emeritus' new DS1511 RTC board.  Allows autobooting with F1 (use 'autoboot -a' as root to enable) and having XENIX come up with the correct time set with no prompting.  In trs80gp, it allows use of Turbo and Haste modes without the XENIX clock speeding up.  You can just leave Turbo on!</li></ul>New Utilities<br/><ul><li>New RTC utility /etc/hwclock, which allows querying and setting of the RTC. Setting is not supported in trs80gp.</li><li>New version of /etc/cfg to support all the latest kernel features in XENIX 3.4.</li><li>Updated /bin/as (68000 assembler) with a bug fix for long assembly macros.</li><li>New version of /etc/getty which displays both the system name and the terminal in the banner.</li><li>New version of /etc/shutdown which supports being linked to /etc/reboot, and also now allows "-n" in front of the kernel-name argument.</li><li>New /etc/reboot link to /etc/haltsys which reboots the system instead of halting.</li><li>New and updated help pages for all of the above.</li></ul> |
| chown.tar.gz | 9,049 | Port of BSD chown, which can change owner and group simultaneously, and can recursively change directory trees.  Its usage looks like this:<br/><tt><nobr>&nbsp;&nbsp;&nbsp;usage:chown[-R] user[.group] file ...</nobr></tt> |
| games.tar.gz | 1,618,521 | From the README:<br/><tt>These games are an amalgamation of various XENIX games disks, as well as some items off the internet that were ported by me because I remember having fun playing them.  To be able to play some of the games, you may need to use cfg to increase maxmem larger than the default 256k. You will note that UID 11 and GID 11 own everything on this archive. These games were setup to have a games owner and games group.  The reason is some of the games need setgid and some need setuid. Set them up like this:</tt><br/><br/><tt>&nbsp;&nbsp;/etc/passwd:&nbsp;games:NOLOGIN:11:11:Owner of Games:/usr/games:</tt><br/><nobr><tt>&nbsp;&nbsp;/etc/group:&nbsp;<nobr>games:x:11:games</nobr></nobr></tt><br/><br/><tt>I fixed the scoreboard problem with nethack!  It had a Y2K bug that corrupted the entries in the scoreboard.</tt><br/><br/><tt>I have added documentation where I had it or could find it.  It is pre-formatted and is all in /usr/games/Help.  The directory /usr/games/Doc has the man page source when available; you'll note that not all games' help files are man pages, some are just text files.  I have also added a new command for getting games help, /usr/games/ghelp.  It works much like the XENIX help command does, except there are no sections.</tt><br/><br/><tt>The games provided with this file are unsupported and undocumented.  They are provided as-is without any warranty whatever, and nobody accepts any liability for unintentional or malicious damage caused by use of them.  Do not use the games while running with root privileges.</tt><br/><br/><tt>The games do have bugs in them. For instance, if you run adventure through too many save/restore game cycles, you will run out of memory.  One will probably work, 10 might work, 20 is iffy, and 1,000 will cause problems. (An adventure "saved game" is an executable file which you run to restart the game.)</tt> |
| gcc&#8209;1.24.tar.gz | 305,733 | A gcc that works on XENIX; I believe this was ported by Gordon L. Burditt.<br/><b>Warning:&nbsp;</b>You will need to use cfg and set maxmem as high as <b>3072k</b>for it to work. (I had to set it to 3072k to be able to compile vim 4.5.) |
| gzip.tar | 34,442 | This is gzip and gunzip for XENIX.  Lets you uncompress the other files.  'nuff said. |
| rcs&#8209;5.7.tar.gz | 337,710 | I ported RCS v5.7 to XENIX so that I can use it for new stuff I make, and so all the stuff from the Frank Durda Archives can be looked at on a XENIX system. |
| vim&#8209;4.5.tar.gz | 491,355 | I really, really missed VIM's ability to have multi-windows in a VI session when I started using XENIX again, which only had vanilla vi. So, I went back a ways and found a copy of vim's 4.5 source hoping it'd be close enough for porting.  It took a couple of weeks, but I got it working!!!<br/><b>Note:</b>You <u>will</u> need to use cfg to set maxmem to a minimum of 1024k for it to work. |
||| <b>Do <u>NOT</u> install the files below on a XENIX 3.4 system.  It already has newer versions.</b> |
| getty.tar | 23,552 | Modified getty which displays the name of the terminal you are on.  This is mainly of interest to those using XEINX 3.3's virtual consoles. The banner now looks like this:<br/><nobr>&nbsp;&nbsp;<tt>Tandy 68000/XENIX v03.03.00 (sysname) [ttyc1]</tt></nobr><br/>Of course, 'sysname' will be your system name as set with cfg. The tar file contains BOTH the new getty and the original 3.3 getty, so you don't have to rename /etc/getty before you extract this. Reboot after extracting. |
| Help&#8209;cfg&#8209;adj_clock.tar | 17,408 | I recreated the missing manual pages for those two new admin commands, cfg and adj_time, from the scanned versions (I wrote new roff source in man format and then formatted them for use by help).  On cfg's page I went a little further and brought it up-to-date with the current cfg. |