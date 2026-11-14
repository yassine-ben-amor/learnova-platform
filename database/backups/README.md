# Backup and Restore

Scripts to back up and restore the Learnova PostgreSQL database.

| File | Platform | Description |
| :--- | :--- | :--- |
| `backup.sh` | Linux / macOS / WSL | Timestamped backup in PostgreSQL custom format |
| `restore.sh` | Linux / macOS / WSL | Full restore from a backup file |
| `backup.bat` | Windows | Timestamped backup |
| `restore.bat` | Windows | Guided restore |

## Configuration

Set the connection variables before running a script:

```bash
export DB_HOST="localhost"
export DB_PORT="5432"
export DB_NAME="learnova"
export DB_USER="learnova"
export PGPASSWORD="your_password"
```

## Back up

```bash
./database/backups/backup.sh
```

On Windows:

```cmd
cd database\backups
backup.bat
```

Backups are written to `database/backups/archives/` as `learnova_backup_YYYYMMDD_HHMMSS.dump`. This folder is ignored by Git.

## Restore

```bash
./database/backups/restore.sh database/backups/archives/learnova_backup_YYYYMMDD_HHMMSS.dump
```

On Windows:

```cmd
restore.bat archives\learnova_backup_YYYYMMDD_HHMMSS.dump
```

## Scheduled backups

To run a daily backup at 02:00 with cron:

```cron
0 2 * * * /path/to/learnova-platform/database/backups/backup.sh >> /var/log/learnova_backup.log 2>&1
```

`backup.sh` deletes backups older than 30 days.
