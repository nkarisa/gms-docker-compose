# gms-docker-compose


# Grant "Trust" to Function Creators 
`docker compose exec mysql-server mysql -u"$MYSQL_USER" -p"$MYSQL_PASSWORD" -e "SET GLOBAL log_bin_trust_function_creators = 1;"`

# Transferring a SQL schema file from your web server container directly into your MySQL database container to execute it

`docker compose exec -T web-server sh -lc 'cat /var/www/html/app/Database/Sql/schema.sql' | docker compose exec -T mysql-server sh -lc 'mysql -u"$MYSQL_USER" -p"$MYSQL_PASSWORD" "$MYSQL_DATABASE"'`

