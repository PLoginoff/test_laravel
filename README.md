General Description

The test task is to make parser of user data.

Each day or each few hours, csv file is received that need to be synced to db.

The goal of the parser is to synchronized the db of the project with the file received. Meaning we need to remove (soft delete) all the users that are not in the file and update/create the rest.

Report need to be generated with the details.

The input file can contain between 500 to 150k rows and the db can contain few millions of rows (including soft deleted)

Performance and memory consumption are important for the process.



The columns of the file are:

Identifier - unique identifier of the user 

First Name

Last Name

Card Number

User email 



Identifier and Card number need to be unique



The parser needs to do validation (correct data format, no duplicates ....)

In case some row cannot be parsed - the file is rejected.

In case some row fails in validation - reject only this row.
In case there is a duplicate, we reject both.
In any case, we do not fail parsing because of some rejected row.

The data received should have a mapping for each column, since it might be received in one format, but stored in another or we can take data from multiple columns and combine it into one that will be stored eventually.

The parser needs to update user’s database with mapped values.

All the entries that are no longer in the file, but exist in db need to be removed (soft delete)
Any new entry - need to be added
Any existing entry - should be updated
Any entry that is currently deleted in the db, need to be restored.

Report need to be generated as csv files for each type for the following:
Rows where that failed validation, with reason/s of fail
Rows that were added - we need to show for values that were added.
Rows that were updated - we need to show for values that were changed previous and new value.
Rows that were removed - we need to show all the values that were before removal
Rows that were restored - we need to show for values that were changed previous and new value.

Summary of the result need to be printed to log/console
Status passed/failed
How many new/deleted/restored/updated/rejected.

Test requirements.
Before starting the task, implementation need to provide time estimate for full solution.
As part of the test need to implement main parts with code, the rest can stay as stubs.
The code needs to be clear and documented in same way as it would be in real project.
The code needs to be written in a way that allow easy modification for validations/adding new columns/changing mapping/making some additional fields unique….

