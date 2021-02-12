# DiskBackup
Make a Full Disk Backup with DD in Linux

Make a Full Disk Backup with DD ==>

dd if=/dev/sdc conv=sync,noerror status=progress bs=64K | gzip -c > backup_image.img.gz

Restoring a Full Drive Backup with DD ==>

gunzip -c backup_image.img.gz | dd of=/dev/sdc status=progress

<br/>
ref:<br/>
https://bdoga.com/full-disk-backup-with-dd/<br/>https://www.linux.com/topic/desktop/full-metal-backup-using-dd-command/<br/>

=============== Alternatively ===========================<br/>
syntax -><br/>
rsync options SOURCE DESTINATION<br/>

eg:<br/>
sudo rsync -av --progress --stats /media/user_name/drive1/  /media/user_name/drive2/

compress backup --><br/>

sudo tar -zcvf your_file.tar.gz your_file/  && sudo rsync -avz --progress --stats your_file.tar.gz shiv@xxx.xxx.x.xxx:/mnt/your_dir/dir/dir/ && sync && rm your_file.tar.gz
<br/>

decompress --> <br/>

tar -zxvf your_file.tar.gz

=============== Alternatively ===========================<br/>
ddrescue ==><br/>
ref:<br/>
https://www.technibble.com/guide-using-ddrescue-recover-data/ <br/>
https://datarecovery.com/rd/how-to-clone-hard-disks-with-ddrescue/
     
=============== Alternatively ===========================<br/>
compress backup --><br/>

In same machine --> <br/>
tar zcvf destination_path/your_file.tar.gz source_path && sync

In different machine --> <br/>
tar zcvf - /wwwdata | ssh vivek@192.168.1.201 "cat > /backup/wwwdata.tar.gz" && sync<br/>

decompress --> <br/>

ssh remotehost cat /path/to/foo.tar.gz | tar zxvf - && sync

ref: <br/>
https://www.cyberciti.biz/faq/howto-use-tar-command-through-network-over-ssh-session/<br/>
https://www.computernetworkingnotes.com/linux-tutorials/create-and-restore-incremental-backups-in-linux-with-tar.html<br/>
https://stackoverflow.com/questions/50796631/how-do-i-extract-a-remote-tarball-on-to-local-machine <br/>
     
