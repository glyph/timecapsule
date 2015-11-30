timecapsule
===========

Supports Apple Time Machine backup by using netatalk to look like a time capsule.

Features:
- Use net="host" for Bonjour support
- Volume /backup to store the backup, may use a data container or host mount
- VOLPATH environment variable to override /backup for backup storage
- Volume /log used to store log, in addition to output of log in console
- Volume size limit defaults to 500000KB (~500GB), set using VOLSIZELIMIT environment variable in KB units
- PUID and PGID to (optionally) set user and group

