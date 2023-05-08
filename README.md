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
Also, dont' forget to choose your edition of Windows properly. And, to trigger the
command prompt, use the shortcut Shift+F10 in the installer. Or, just watch the video on my 
Tech channel @TechLivieOfficial2023.]
