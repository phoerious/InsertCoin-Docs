# Free some space on phone's memory without DATA2EXT

Although there is a2sd, that keeps the apks on the sd-ext some files are stored
on phone's nand on `/data partition` and if we install a lot of apks then you remain
out of free space. *WE DO ALL THIS WITH PHONE ON, NOT IN RECOVERY*.

1st let's see how much free space I'm having:

    # df -h | grep data
    /dev/block/mtdblock5 147.6M 76.7M 70.9M 52% /data  

As you can see I have left about 70 MB free. Lets see what folders eat my space:

    # du -sk /data/data/* | sort -rn | head
    18641 /data/data/com.navngo.igo.javaclient
    14911 /data/data/com.opera.browser
    6756 /data/data/com.google.android.gm
    5194 /data/data/com.android.providers.contacts
    3661 /data/data/com.htc.launcher
    3083 /data/data/com.htc.googlereader
    1276 /data/data/com.swype.android.inputmethod
    1172 /data/data/com.android.settings
    1144 /data/data/com.htc.android.mail
    1084 /data/data/and.blogger

Ok so it seems that iGO and Opera are eating 32 megs together. I'll leave
`data/data/com.google.android.gm` alone since it's Gmail and I want to be more
responsive by keeping its files to nand (I only have a class 4 card). Lets get to
work. 1st we need to make a folder on sd-ext where to keep the files. 

    # mkdir /system/sd/.moreapps  

I made the folder `.moreapps`. Now let's move stuff and symlink them.

First we move them:

    # mv /data/data/com.navngo.igo.javaclient /system/sd/.moreapps/com.navngo.igo.javaclient

Then we symlink them:

    # ln -s /system/sd/.moreapps/com.navngo.igo.javaclient /data/data/com.navngo.igo.javaclient

Now we repeat the operation for opera. Move:

    # mv /data/data/com.opera.browser /system/sd/.moreapps/com.opera.browser  

Symlink:

    # ln -s /system/sd/.moreapps/com.opera.browser /data/data/com.opera.browser  

Now let's check again my free space. 

    # df -h | grep data
    /dev/block/mtdblock5 147.6M 51.8M 95.9M 35% /data 

Well it seems to me I gained 35 MB without uninstalling apps, without moving
ALL of them to SD and experience some lags. 

Now let's check if we made the symlinking right

    # ls -al --color=none /data/data/com.opera.browser
    lrwxrwxrwx 1 0 0 38 Feb 22 05:46 /data/data/com.opera.browser -> /system/sd/.moreapps/com.opera.browser  

Yap all seems right. Opera and iGO are working at same speed, I freed up some
space. Everyone's happy.

The advantage of this method is that you can choose what to move to sd-ext you
don't have to have all to sd-ext. 
Now make sure you don't name your folder in `/system/sd` "data" since a2sd
script will move back on nand all its contents. 

This method is recommend for GPS software, Browsers, Games, some apps you got
from market. It's best to  leave system apps there to avoid FCs or slowdowns.
If anything goes wrong with your app after this you can always move them back.
1st you delete the symlink (`rm /data/data/whatevar`) then move it back.