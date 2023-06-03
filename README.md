QUERY questions: 

mysql> INSERT INTO movies (movieTitle,runTime, genre, imdbScore, rating)
    ->   VALUES('Avengers Endgame', 182, 'Action',8.4, 'PG-13');
Query OK, 1 row affected (0.01 sec)

mysql> INSERT INTO movies (movieTitle,runTime, genre, imdbScore, rating)
    ->   VALUES('The Dark Knight', 152, 'Action',9, 'PG-13');
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM movies WHERE genre='Sci-Fi';

mysql> SELECT * FROM movies WHERE imdbScore <=6.5;

mysql> SELECT * FROM movies WHERE runTime < 100 AND (rating = 'G' OR rating = 'PG');

mysql> SELECT genre, AVG(runTime) AS average_runtime
    -> FROM movies
    -> WHERE imdbScore < 7.5
    -> GROUP BY genre;

mysql> UPDATE movies SET rating = 'R' WHERE movieTitle='Starship Troopers';

mysql> SELECT productID, rating
    -> FROM movies
    -> WHERE genre IN ('Horror', 'Documentary');

mysql> SELECT MAX(imdbScore), MIN(imdbScore), AVG(imdbScore) FROM movies;

mysql> SELECT MAX(imdbScore), MIN(imdbScore), AVG(imdbScore), rating
    -> FROM movies
    -> GROUP BY rating
    -> HAVING COUNT(*) > 1;

mysql> DELETE FROM movies WHERE rating='R';

final table result: 

+-----------+------------------+---------+-----------+-----------+--------+
| productID | movieTitle       | runTime | genre     | imdbScore | rating |
+-----------+------------------+---------+-----------+-----------+--------+
|         1 | Howard The Duck  |     110 | Sci-Fi    |       4.6 | PG     |
|         2 | Lavalantula      |      83 | Horror    |       4.7 | TV-14  |
|         5 | Spaceballs       |      96 | Comedy    |       7.1 | PG     |
|         6 | Monsters Inc.    |      92 | Animation |       8.1 | G      |
|         7 | Avengers Endgame |     182 | Action    |       8.4 | PG-13  |
|         8 | The Dark Knight  |     152 | Action    |       9.0 | PG-13  |
+-----------+------------------+---------+-----------+-----------+--------+








