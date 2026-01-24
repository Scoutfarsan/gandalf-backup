# gandalf-backup

Backup-system för Gandalf (Raspberry Pi) med:
- Full backup + incremental (tar --listed-incremental)
- Rclone upload till Google Drive
- Routing till full/inc/logs
- Retention/cleanup

## Struktur
- scripts/  : körbara scripts
- systemd/  : unit-filer, timers och drop-ins

## Install (skiss)
Kopiera scripts till /usr/local/sbin och unit-filer till /etc/systemd/system, kör:
- systemctl daemon-reload
- systemctl enable --now <timers>
