# Audit your schema

[link](https://forum.codequalitychallenge.com/t/day-22-audit-your-schema/821)

It’s time to turn an eye toward your database schema.

Please spend 20 minutes reading through yours carefully.

Some things you might look for:

    Inconsistent column names.
    Missing indices for columns you frequently query by.
    Missing unique indices to ensure uniqueness.
    Missing null constraints.
    Missing foreign key constraints.
    Maybe even install bullet3 to detect N+1 queries in activerecord and mongoid.
