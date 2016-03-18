# twrp_samsung_kanas3gnfcxx
Device configuration for Samsung Galaxy Core II SM-G355HN For TWRP Only 
android_device_samsung_kanas3gnfc
===================================

                       instruction how to build

I think you already set up build enviroment so I will skip this.

After you finshed repo sync (cm sources) go in your working dir ../device/
and create folder /samsung/kanas3gnfc and copy content of kanas3gnfc
that you downloaded from here.
Replace (CM) android/bootable/recovery whit this one : https://github.com/omnirom/android_bootable_recovery

Than run comannd in terminal from your working dir

        . build/envsetup.sh
        lunch omni_kanas3gnfc-userdebug
        make recoveryimage

Your build will start and you will find your recovery. img in
your working dir ../out/target/product/kanas3gnfc

To make it flashable via ODIN you have to make it recovery.tar.md5
Navigate with terminal where your recovey.img is.
For example cd android/out/target/product/kanas3gnfcxx
where android is name of your working dir
and run comands:

        tar -H ustar -c recovery.img > recovery.tar
        md5sum -t recovery.tar >> recovery.tar
        mv recovery.tar recovery.tar.md5
        
An now you got recovery.tar.md5 ready to be flashed usin ODIN selected as PDA file

Happy building.



