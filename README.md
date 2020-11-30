# incrsync
An incremental backup utility built on rsync (https://rsync.samba.org/). The main script uses a suggested implementation found on https://linuxconfig.org/how-to-create-incremental-backups-using-rsync-on-linux and includes basic checks for handling command line arguments`.

## Usage
```bash
incrsync [options] STORAGE_DIR BKP_ROOT EXCL_FILE

Optional arguments:
  -h or --help      Display this message and exit

Positional arguments:
  STORAGE_DIR       The parent directory for storing the incremental backups
                    and logs. Note that this script creates a directory for
                    storing logs but does not write there itself. You must use
                    output redirection to write there (defaults to
                    STORAGE_DIR/log). logrotate can optionally be used to manage
                    the rotation and size of these logs.
  BKP_ROOT          The root directory to backup.
  EXCL_FILE         Path to a file that contains exclude patterns for rsync.
                    This path will be passed to rsync's --exclude-from option.
                    See 'man rsync' for information on how to use this feature.
```

Also included in this repository:
1. A sample logrotate configuration file: sample_incrsync_logrotate.conf
1. A sample rsync exclusions file: sample_rsync_exclusions

## License
This software is currently licensed under GNU Affero General Public License v3.0. See the attached 'LICENSE' file or go to https://www.gnu.org/licenses/agpl-3.0.html for more information. I have included a license with this repository so that the author of the suggested implemented found on https://linuxconfig.org/how-to-create-incremental-backups-using-rsync-on-linux can also receive recognition for the effort that they put into building their excerpt.

