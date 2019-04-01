numbers are correspond to step numbers of git bisect

what are those files?
git_bisect_log.txt is bisect log.
-1 is not considered anything, its just a random log.
*.1 folders are "second time booting the same kernel to be sure".
original4.14 is for referance on healthy kernel.
final_results.txt is final results.

script that i run to benchmark:

sudo su -c 'pkill -fxc -15 /usr/bin/boinc;systemctl stop boinc-client';(echo '#####'&&echo&&echo "beginning of 'journalctl -b0'"&&echo&&echo '#####'&&journalctl -b0&&echo '#####')>log.txt&&sh -c 'cd /home/utku2/Programlar/Xonotic/&&vblank_mode=0 DRI_PRIME=1 ./xonotic-linux64-glx -benchmark demos/the-big-keybench.dem'&&(echo&&echo beginning of xonotic benchmark results&&echo&&echo '#####'&&tail -n1 /home/utku2/.xonotic/data/benchmark.log&&echo '#####'&&echo&&echo "beginning of 'journalctl -b0'"&&echo&&echo '#####'&&journalctl -b0&&echo '#####')>>log.txt

sometimes error messages pop-up while booting, so i just run "journalctl -b0>it_allready_failed.txt" on those boots.

I have started bisecting with this command:

git bisect start 320b164abb32db876866a4ff8c2cb710524ac6ea 0adb32858b0bddf4ada5f364a84ed60b196dbcda -- drivers/gpu/drm/amd