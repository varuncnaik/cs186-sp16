## Section 2

Topics: advanced SQL, 6 degrees of separation in SQL, median in SQL

This directory includes a file discussion.db, with the
Albums/Artists/Songs schema from the worksheet. To play around with the
data, run the following command on a Linux or Mac machine, using
Cygwin or Git Bash on Windows, in your Vagrant VM, or on an
instructional machine:

    $ sqlite3 discussion.db

This should open the SQLite interpreter. Here are some commands you
can run to get started:

    sqlite> .tables
    albums   artists  songs  
    sqlite> .schema
    CREATE TABLE songs
             (song_id integer primary key,
              song_name text,
              album_id integer,
              weeks_in_top_40 integer);
    CREATE TABLE artists
              (artist_id integer primary key,
               artist_name text,
               first_year_active datetime);
    CREATE TABLE albums
              (album_id integer primary key,
              album_name text,
              artist_id integer, 
              year_released datetime,
              genre text);
    sqlite> SELECT COUNT(*) FROM albums;
    16025
    sqlite> .quit

Here is the median example I used in discussion:

    sqlite> WITH RECURSIVE cnt(x) AS (
       ...>   SELECT 1
       ...>   UNION
       ...>   SELECT x+1 FROM cnt LIMIT 99
       ...> )
       ...> SELECT T.x AS median FROM cnt T WHERE
       ...> (SELECT COUNT(*) FROM cnt T1 WHERE T1.x <= T.x)
       ...> =
       ...> (SELECT COUNT(*) FROM cnt T2 WHERE T2.x >= T.x);
    50

