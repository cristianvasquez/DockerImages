# Tabula-rest

A docker image that provides a rest-wrapper to be invoked by the pipeline.

```
docker build -f tabulaRest.Dockerfile -v `pwd`/data:/data -t cvasquez/rest-tabula .

docker run --rm -p 8080:8080 cvasquez/rest-tabula
```

