# membership_archeology
sql and more for finding what is hidden in CiviCRM!

## getting current membership counts
Just use the same code as the historical counts. Don't trust Civi, because it relies on cron jobs to set membership status. This happens late, and race conditions are certain to happen.

## getting historical membership counts
civicrm_membership_log is treated as the gound truth. civicrm_membership is only used to map the relations between membership, contact, and membership_log.

civicrm_activity is used to produce mapping of so called "merged and deleted" contacts

## next steps
- Provide a few canned queries to get final reports (daily/monthly totals, etc)
- Put this in a pretty graph
