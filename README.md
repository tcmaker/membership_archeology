# membership_archeology
sql and more for finding what is hidden in CiviCRM!

## getting current membership counts
Just use the same code as the historical counts. Don't trust Civi, because it relies on cron jobs to set membership status. This happens late, and race conditions are certain to happen.

## getting historical membership counts
civicrm_membership_log is treated as the gound truth, although log entries may be missing for very old memberships. civicrm_membership is only used to map the relations between membership, contact, and membership_log.

## caveats
So called "merged and deleted" contacts may be double reported here. See activity codes 55 and 51 to remediate

## next steps
- Clean up SQL, probably make the collapsed_log table into a view.
- Break down memberships by type
- Create views to get more intermediate data
- Provide a few canned queries to get final reports from said views (daily/monthly totals, etc)
- Put this in a pretty graph
