# ODOO 10 CON DOCKER
Dockerfile per la creazione di un'immagine odoo 10.





### Creo immagine a partire dal Dockerfile
```
docker build -t odoo10 .
```

### Creo immagine a partire Myodoo10 personalizzata
```
docker build -t myodoo10 ./myodoo10
```

### Creare il docker database postgress

```
docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --name db_odoo10 postgres:10
```

### Creare container odoo10
```
docker run -p 8200:8069 --name odoo10 --link db_odoo10:db -t odoo10
```
### Creare container odoo10 con addons in locale
```
docker run -p 8200:8069 --name odoo10 -v /Users/enricoalterani/github/odoo10_docker/addons:/mnt/extra-addons --link db_odoo10:db -t odoo10
```

### Creare container myodoo10
```
docker run -p 8200:8069 --name myodoo10 --link db_odoo10:db -t myodoo10
```


### FATTO!
per acceddere a oddo dal propio borwser e creare il proprio database e la propria configurazione:

http://192.168.99.100:8200

Sottare il servizio 
docker stop odoo10

Avviare il servizio
docker start odoo10


## Avanzate

### Per aprire una shell all'interno del  docker (odoo10 è il nomer del container)
Accesso con utente odoo
```
bash -c "clear && docker exec -it odoo10 bash"
```
Accesso con utente root
```
bash -c "clear && docker exec -u 0 -it odoo10 bash"
```



### Per aprire una shell all'interno del  DATABASE (db_odoo10 è il nomer del container)
```
bash -c "clear && docker exec -it db_odoo10 bash"
```
Appena connessi alla schel per loggarsi nel database:
```
psql -U odoo -W test
```


