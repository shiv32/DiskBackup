# DiskBackup
Make a Full Disk Backup with DD in Linux

Ref: https://bdoga.com/full-disk-backup-with-dd/<br/>https://www.linux.com/topic/desktop/full-metal-backup-using-dd-command/

Make a Full Disk Backup with DD ==>

dd if=/dev/sdc conv=sync,noerror status=progress bs=64K | gzip -c > backup_image.img.gz

Restoring a Full Drive Backup with DD ==>

gunzip -c backup_image.img.gz | dd of=/dev/sdc status=progress

=============== Alternatively ===========================

sudo rsync -av /media/user_name/drive1/  /media/user_name/drive2/

=============== Alternatively ===========================
ddrescue ==>
ref: https://www.technibble.com/guide-using-ddrescue-recover-data/ <br/>
     https://datarecovery.com/rd/how-to-clone-hard-disks-with-ddrescue/
