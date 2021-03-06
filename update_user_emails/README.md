# Mass Update PagerDuty User Emails

If you plan on changing your domain/branding, or your organization is
undergoing an acquisition (for instance), you can use this script to update
login email addresses (and contact method addresses) en masse according to
search/replace patterns or a CSV file with email addreses of users (and the
addresses that will replace them).

Example: Replace all instances of example1.com in users' email addresses with
example2.com.

```
# Using plain search and replace:
# Note, this would not work as intended to replace the domain if any user's
# email address (before the `@`) contained `example1.com`
./update_user_emails.py -k API-KEY -q example1.com -r example2.com

# Using regex (more precisely):
./update_user_emails.py -k API-KEY -q example1.com -e '([^@]+)@example1.com' -r '\1@example2.com'
```

Note, you can preview the change before enacting it by running the script with
the `-n` flag.
