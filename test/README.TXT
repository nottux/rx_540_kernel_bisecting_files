numbers are correspond to step numbers of git bisect

what are those files?
git_bisect_log.txt is bisect log
-1 is not considered anything
original4.14 is for referance on healthy kernel

script that i run:

sudo su -c 'pkill -fxc -15 /usr/bin/boinc;systemctl stop boinc-client';(echo '#####'&&echo&&echo "beginning of 'journalctl -b0'"&&echo&&echo '#####'&&journalctl -b0&&echo '#####')>log.txt&&sh -c 'cd /home/utku2/Programlar/Xonotic/&&vblank_mode=0 DRI_PRIME=1 ./xonotic-linux64-glx -benchmark demos/the-big-keybench.dem'&&(echo&&echo beginning of xonotic benchmark results&&echo&&echo '#####'&&tail -n1 /home/utku2/.xonotic/data/benchmark.log&&echo '#####'&&echo&&echo "beginning of 'journalctl -b0'"&&echo&&echo '#####'&&journalctl -b0&&echo '#####')>>log.txt