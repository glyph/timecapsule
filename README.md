timecapsule [![CircleCI](https://circleci.com/gh/double16/timecapsule.svg?style=svg&circle-token=6060fdc30159f0f2ec2ca16dfbc0861e843e50e9)](https://circleci.com/gh/double16/timecapsule)
===========

[![](https://images.microbadger.com/badges/image/pdouble16/timecapsule.svg)](http://microbadger.com/images/pdouble16/timecapsule "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/pdouble16/timecapsule.svg)](http://microbadger.com/images/pdouble16/timecapsule "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/commit/pdouble16/timecapsule.svg)](http://microbadger.com/images/pdouble16/timecapsule "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/license/pdouble16/timecapsule.svg)](http://microbadger.com/images/pdouble16/timecapsule "Get your own version badge on microbadger.com")

Supports Apple Time Machine backup by using netatalk to look like a time capsule.

Features:
- Use net="host" for Bonjour support
- Volume /backup to store the backup, may use a volume or host mount
- VOLPATH environment variable to override /backup for backup storage
- Volume size limit defaults to 500000KB (~500GB), set using VOLSIZELIMIT environment variable in KB units
- PUID and PGID to (optionally) set user and group

Authenticate to the Time Capsule volume using user `timecapsule` and password `timecapsule`. Due to the fixed password, do not expose this service to untrusted environments.

Example `docker-compose.yml`:
```yaml
version: "2"

volumes:
  timecapsule:

services:
  timecapsule:
    image: pdouble16/timecapsule:3.1.10
    restart: always
    ports:
      - "548:548"
    environment:
      - VOLSIZELIMIT=1000000
    volumes:
      - timecapsule:/backup
```

