mountvol
D:
dir/w
cd sources
diskpart
lis dis
sel dis 0/1(depends on the number by which your partition is denoted)
lis par
conv gpt (if using Legacy, use MBR)
cre par efi size=512
form fs=fat32 quick
ass letter w
lis par
cre par pri
form quick
ass letter z
exit
dism /apply-image /imagefile:install.wim /index:4 /applydir:Z:\
bcdboot Z:\Windows /s W:
wpeutil reboot
[NOTE: Do NOT boot from USB, rather, let it boot from the hard disk(system partition).
Also, if you plan on adding a personal Windows account, do it once you finish 
setting up Windows by first using a local account, then add your MS account via System
settings. Make sure you have an internet connection.]
