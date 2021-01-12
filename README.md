# DiskBackup
Make a Full Disk Backup with DD in Linux

Ref: https://bdoga.com/full-disk-backup-with-dd/

Make a Full Disk Backup with DD ==>

dd if=/dev/sdc conv=sync,noerror status=progress bs=64K | gzip -c > backup_image.img.gz

Restoring a Full Drive Backup with DD ==>

gunzip -c backup_image.img.gz | dd of=/dev/sdc status=progress
