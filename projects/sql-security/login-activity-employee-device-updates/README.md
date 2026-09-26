# SQL Filtering: Login Activity and Employee Device Updates

## Overview

I used SQL to retrieve and filter security-relevant information from a simulated organization's database. The work focused on two tasks: reviewing authentication activity for potentially suspicious logins and identifying employees whose devices required security updates.

Using the `log_in_attempts` and `employees` tables, I applied SQL filtering conditions to isolate relevant records without reviewing the entire database manually.

## Login Activity Review

### Failed Login Attempts After Business Hours

I filtered authentication records to identify unsuccessful login attempts after 18:00.

```sql
select * from log_in_attempts where login_time > '18:00' and success = 0;
```

**Result:** 19 failed login attempts after 18:00.

### Login Activity on Specific Dates

I retrieved login records from May 8 and May 9, 2022, to review authentication activity surrounding a reported suspicious event.

Using `OR` allowed records from both dates to be included in the results.

**Result:** 75 login attempts across the two dates.

### Login Attempts Outside Mexico

I used `NOT LIKE` with the `%` wildcard to exclude records associated with Mexico.

The country field contained both `MEX` and `MEXICO`, so matching the shared prefix allowed both values to be excluded in a single condition.

**Result:** 144 login attempts outside Mexico.

## Employee Device Update Review

I also used SQL to identify employees whose devices required security updates.

The queries targeted three groups:

- Marketing employees working in the East building
- Employees in Finance or Sales
- Employees outside the Information Technology department

The filters combined department and office information to retrieve the relevant employee records.

The final query excluded Information Technology employees because their security updates had already been completed.

**Result:** 161 employees outside the Information Technology department.

## Security Relevance

The queries supported two practical security workflows.

For login investigations, filtering made it possible to focus on authentication records associated with specific times, dates, and locations.

For device-update planning, the queries identified employee groups requiring attention based on department and office location.

These results provided a more focused starting point for reviewing login activity and organizing security updates across the organization.

## Skills Demonstrated

- SQL querying and filtering
- Database record retrieval
- Authentication-log analysis
- Security investigation support
- Employee-record filtering
- Security update planning
- Boolean filtering with AND, OR, and NOT
- Pattern matching with LIKE and wildcards
- Technical documentation

## Completed Analysis

[View the completed SQL filtering report](./sql-filtering-login-activity-employee-device-updates.pdf)

## Project Context

This work was completed in a simulated educational environment. The database and security scenarios were provided; the SQL queries, filtering approach, analysis, and portfolio report reflect my work.
