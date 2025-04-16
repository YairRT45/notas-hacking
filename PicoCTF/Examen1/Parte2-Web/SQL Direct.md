Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 58530 -U postgres pico`Password is `postgres`

Hints:
1. What does a SQL database contain?


## Solución:
Primero revisamos que tablas existen en la base de datos:
```
pico=# SELECT table_schema, table_name FROM information_schema.tables WHERE table_schema NOT IN ('pg_catalog', 'information_schema') ORDER BY table_schema, table_name;

 table_schema | table_name 
--------------+------------
 public       | flags
(1 row)
```
Ahora revisamos el contenido de la tabla flags:
```
pico=# SELECT * FROM flags;

 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)
```

```
picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
```