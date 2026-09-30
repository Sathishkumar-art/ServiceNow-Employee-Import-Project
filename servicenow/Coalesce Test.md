# Coalesce Test

Set **Employee ID** as the Coalesce field in the Transform Map field mappings.

Expected behavior:
- Same Employee ID + changed values -> update the existing record.
- New Employee ID -> insert a new record.
- Re-uploading unchanged data -> no duplicate records are created.

Check Transform History for inserted, updated, and ignored rows.
