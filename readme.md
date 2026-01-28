

## Docker how to
When not having vue and node installed, the following commands can be used:

```
> docker build . -t send-tx 
> docker run --rm -p 5173:5173 send-tx
```

Notice that editing the vue code requires to rebuild the docker container (as it
contains a build of the vue program itself)