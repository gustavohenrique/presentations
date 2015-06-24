# docker para desenvolvedores

> Palestra realizada no espaço coworking da EDX com apoio da Jaws-IT no dia 23/06/2015

## Slide

Para visualizar os slides, abra o arquivo `slides/index.html`.

## Exemplos

### nginx

```
docker build -t=jawsit/nginx -f Dockerfile-nginx .
docker run -d -p 80:80 jawsit/nginx
```

### gedit

```
brew install socat
socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\" # em outro terminal
docker build -t=jawsit/gedit -f Dockerfile-gedit .
docker run -ti -e DISPLAY=<coloque seu ip>:0 -v /tmp/.X11-unix:/tmp/.X11-unix jawsit/gedit
```

### deploy no heroku

```
cd node-js-getting-started
heroku apps:create docker-para-desenvolvedores
heroku docker:release # deve instalar o docker plugin antes
```


