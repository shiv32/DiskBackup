# DiskBackup
Make a Full Disk Backup with DD in Linux

Ref: https://bdoga.com/full-disk-backup-with-dd/<br/>https://www.linux.com/topic/desktop/full-metal-backup-using-dd-command/

Make a Full Disk Backup with DD ==>

dd if=/dev/sdc conv=sync,noerror status=progress bs=64K | gzip -c > backup_image.img.gz

Restoring a Full Drive Backup with DD ==>

gunzip -c backup_image.img.gz | dd of=/dev/sdc status=progress

=============== Alternatively ===========================<br/>
syntax -><br/>
rsync options SOURCE DESTINATION<br/>

eg:<br/>
sudo rsync -av --progress --stats /media/user_name/drive1/  /media/user_name/drive2/

compress backup --><br/>
sudo tar -zcvf your_file.gz your_file/  && sudo rsync -avz --progress --stats your_file.tar.gz shiv@xxx.xxx.x.xxx:/mnt/your_dir/dir/dir/ && sync && rm your_file.tar.gz
<br/>
decompress --> <br/>
tar -zxvf your_file.tar.gz

=============== Alternatively ===========================<br/>
ddrescue ==><br/>
ref: https://www.technibble.com/guide-using-ddrescue-recover-data/ <br/>
     https://datarecovery.com/rd/how-to-clone-hard-disks-with-ddrescue/
