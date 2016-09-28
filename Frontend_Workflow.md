# Yet Another Frontend Workflow

## @SToneX

---

## Build In FrontEnd

* Vanilla js - ajax web app
* JQuery
* AngularJS
* React & Vue

---

## Workflow In FrontEnd

* Just write in JavaScript
* Use jQuery
* Bower & Grunt & Gulp
* Npm & Webpack

---

## Workflow Now

```
git clone starter-kit@git.xxx.com
npm install
vim package.json
vim webpack.config.js
npm start
```

---

## Node Performance

---

## Dockerize

> "Docker is an open platform for building, shipping and running distributed applications."

* Rapid application deployment
* Portability across machines
* Version control and component reuse
* Sharing of images/dockerfiles
* Lightweight footprint and minimal overhead
* Simplified maintenance

---

## FE Workflow At Shanbay #Currently

```
git clone studyroom@...

# done by ./xxx.sh
docker pull image
docker run -v ${CurDir}:/usr/src/app

# Edit Everything
./xxx.sh build

# 30 minutes later
./xxx.sh start

# need to add a npm package
./xxx.sh build

```

---

Dockerfile

```c
#...
RUN npm i -g \
  ejs@2.4.1 \
  es6-promise@3.1.2 \
  express@4.13.1 \
  request@2.72.0 \
  fs@0.0.2 \
  log@1.4.0 \
  ...
```

Package.json
```json
{
  dependencies: {},
  devDependencies: {},
}
```

---

## Loss

* Self package management
* Can not build without Docker
* Hard to use new package
* ...

---

## Docker + Node

> "Docker is an open platform for building, shipping and running distributed applications."

<https://nodejs.org/en/docs/guides/nodejs-docker-webapp/>

```
COPY package.json /usr/src/app/
RUN npm install

# Bundle app source
COPY . /usr/src/app

EXPOSE 8080
CMD [ "npm", "start" ]
```

---

## Combine Those

```
COPY package.json /usr/local/lib/
RUN npm install

ENV NODE_PATH /usr/local/lib/node_modules
```

---

## Benifit

```sh
git clone ...

# dev local
npm install
npm start

# develop ssh
./xxx.sh start

# build
./xxx.sh build
```

---

## Webpack

* Multi Entry: admin & client & mobile
* CommonChunkPlugin
* HotLoader
* ...


## Express

* middlewares
* webpack-assert
* ...

---

## Yeoman
generator-shanbay
* Generate Everything ...