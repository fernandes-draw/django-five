### Access git django-5 repository
[Git Django-5](https://github.com/PacktPublishing/Django-5-By-Example)


### Pull the PostgreSQL Docker image 
```bash
docker pull postgres:18.1
```

### Start the PostgreSQL Docker container
```bash
docker run --name=blog_db \
  -e POSTGRES_DB=blog \
  -e POSTGRES_USER=blog \
  -e POSTGRES_PASSWORD=xxxxx \
  -p 5432:5432 \
  -d postgres:16.2
```

```bash
python -m pip install psycopg==3.1.18
```

### Command to dumping data from the database to JSON file (if encoding error include -Xutf8 flag after python command)
```bash
python manage.py dumpdata --indent=2 --output=mysite_data.json
```
> **⚠️ IMPORTANTE:** Se você tiver PostgreSQL com PgAdmin4 instalado e em execução, altere a porta da aplicação para 5433 ou qualquer outra porta diferente da padrão do PostgreSQL (5432), ou interrompa o serviço PostgreSQL instalado localmente para evitar conflitos de porta.

### Se ao tentar rodar o migrate com o TrigramExtension falhar, execute este comando no prompt

```bash
docker exec -it blog_db psql -U blog -d blog -c "CREATE EXTENSION pg_trgm;"
```