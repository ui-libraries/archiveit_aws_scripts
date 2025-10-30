## Archive-It Scripts

### `archiveit_date_script.sh`

Downloads WARC files from an **Archive-It** collection (via WASAPI) and uploads any missing files to an **S3 bucket**.  
You can optionally filter by date using the `AFTER_VALUE` variable.

- Example full timestamp: `2025-09-01T00:00:00Z`  
- Or just a simple date: `2025-09-01` (interpreted as midnight UTC)

**Run it with:**
```bash
export COLL_ID=###
export ARCHIVEIT_USER=###
export ARCHIVEIT_PASS=###
export S3_PREFIX=some/path
./archiveit_date_script.sh
```

### `archiveit_recheck_script.sh`

Rechecks **all** WARC files in an **Archive-It** collection (via WASAPI) and uploads any that are missing from an **S3 bucket**.  
No date filter is used — it processes every file. Includes large-file handling by using the expected content length to improve upload reliability.

**Run it with:**

```bash
export COLL_ID=###
export ARCHIVEIT_USER=###
export ARCHIVEIT_PASS=###
export S3_PREFIX=some/path
./archiveit_recheck_script.sh
```

**Summary:**
- Ensures S3 and Archive-It are fully in sync  
- Skips files that already exist in S3  
- Logs new uploads to `new_uploads.txt`
