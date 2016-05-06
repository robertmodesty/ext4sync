*** Ext4 file system Synchronize ***

  This program is written in BASH script for ext4 file system.  It will synchronize the two given directories, include the sub second of modification time.  The files will identified as the same only with the same relative path, name, size and modification timestamp.

  Why not 'rsync'?  For most situation, 'rsync' is useful for synchronize two directories, but it will ignore the sub second which is keeped in ext4 file system, and turn it to zero while copying files.  For a system manager, the sub second may serve as a extra file hash, so it is a better choice to keep it synchronized with the file content.  This is how I start to work on this tiny project.

  I suggest using this program on local directories stored in ext4 file system.  It may not help any thing using it on remote or other file system,  since the sub second maybe removed in transporting or by the file system.  In those situation, 'rsync' is better.

  For running this program, sqlite3 is required.

SYNOPSIS

        e4sync [OPTION]... ORIGIN_DIRECTORY TARGET_DIRECTORY

DESCRIPTION

        -m, --moving-files
        -v, --verbose
