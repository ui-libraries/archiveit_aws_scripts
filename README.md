archiveit_date_script.sh

Downloads WARC files from an Archive-It collection (via WASAPI) and uploads any missing files to an S3 bucket.
You can optionally filter by date using AFTER_VALUE (e.g., 2025-09-01T00:00:00Z) to fetch only newer files. You can also just do...  Date only: 2025-09-01 (interpreted as midnight at the start of that date, UTC)

Run it with:

export COLL_ID=### ARCHIVEIT_USER=### ARCHIVEIT_PASS=### S3_PREFIX=some/path
./archiveit_date_script.sh

archiveit_recheck_script.sh

Rechecks all WARC files in the Archive-It collection (no date filter) and uploads any that are missing from S3.
Includes support for large files by using their expected content length to improve upload reliability.

Run it with:

export COLL_ID=### ARCHIVEIT_USER=### ARCHIVEIT_PASS=### S3_PREFIX=some/path
./archiveit_recheck_script.sh
