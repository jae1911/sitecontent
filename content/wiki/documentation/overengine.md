---
title: "Getting started with Overengine"
---

# Getting started with Overengine

This article will describe how to get started and host your own instance of Overengine.

## Production setup

// TODO

## Dev setup

Setting up a dev repo is pretty simple:

```
git clone https://g.j4.lc/general-stuff/overengine.git
cd overengine
git submodule update --init
yarn
yarn dev
```

This should launch a development server on `http://localhost:8080` ready to be used.

### Docker

To build a local Docker image, use:

```
docker build -t overengine:latest .
```
