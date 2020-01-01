[uber data](https://github.com/fivethirtyeight/uber-tlc-foil-response)


### Create table 

``` SQL
CREATE TABLE trip (
    Dispatching_base_num TEXT,
    Pickup_date TEXT,
    Affiliated_base_num TEXT,
    locationID INTEGER
);

```

### Import csv data

1. create **trip.sqlite3** `sqlite3 trip.sqlite3`

2. enable csv mode `.mode csv`

3. import data from csv file: `.import uber-raw-data-janjune-15.csv trip`


### Benchmarking


#### Sqlite3

Group by Dispatching_base_num: `time echo 'select Dispatching_base_num, count(*) from trip group by Dispatching_base_num;' |sqlite3 trip.sqlite3`
