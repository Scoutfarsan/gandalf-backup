# Gandalf Backup – Cloud-first backup & retention

Cloud-first backup (tar | pigz | rclone rcat) + systemd service/timer + retention + ntfy on failure.

## Designmål
- Ingen lokal lagring (endast temporära loggar)
- Streaming direkt till moln
- Retention i dagar
- Tyst vid OK, notifiering vid fel
- Secrets aldrig i git

## Drift
- Backup: systemd timer (dagligen)
- Cleanup: systemd timer (kväll)

## Restore (exempel)
rclone copy gdrive:backups/<host>/<file>.tar.gz /tmp/
tar -xzf /tmp/<file>.tar.gz -C /

