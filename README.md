# membership_archeology
sql and more for finding what is hidden in CiviCRM!

## getting current or historical membership counts
Don't trust Civi, because it relies on cron jobs to set membership status. This happens late, and race conditions are certain to happen.

Use the view `membership_logs.daily_membership_type_total_aggregate`. You _must_ run `CALL populate_daily_membership_totals('2016-01-01');` to regen the cache before runnung this view if you want current data.

## how we get these numbers
civicrm_membership_log is treated as the gound truth. civicrm_membership is only used to map the relations between membership, contact, and membership_log.

civicrm_activity is used to produce mapping of so called "merged and deleted" contacts

## setup
the `membership_logs` database is fully ephimeral. It can be recreated from scratch by running each `create table` and `create view` command in this repo.

## next steps
- Put this in a pretty graph
