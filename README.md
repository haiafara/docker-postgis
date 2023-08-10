Run the container:

```
docker run \
  --name haiafara-postgis \
  -e POSTGRES_PASSWORD=postgres \
  -v "$PWD/db/data":/var/lib/postgresql/data \
  -v "$PWD/db/extras":/mnt/extras \
  -v /etc/passwd:/etc/passwd:ro \
  --user "$(id -u):$(id -g)" \
  -p 5432:5432 \
  haiafara/postgis
```

Build the image:

```
docker build \
  --progress=plain \
  -t haiafara/postgis \
  .
```
