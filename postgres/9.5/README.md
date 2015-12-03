### postgres 9.5 in docker

postgres will installed under `/usr/lib/postgresql/9.5`.

* expose port: 5432

* build command: `docker build -t postgres:9.5 .`
* run command example: docker run --name some-postgres -e PGDATA=/pgData -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=welcome -e POSTGRES_DB=test_db -d postgres