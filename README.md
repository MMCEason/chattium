# Chattium

Chattium is a tiny chatroom PWA powered by socket.io and create-react-app

## Run Locally

```sh
git clone https://github.com/liuderchi/chattium.git
cd chattium
// start server
yarn && yarn run start:watch
// open another terminal, start client
cd client; yarn && yarn run watch
```

## Develop in Docker Container

1. Clone and run the container with ssh service

```bash
$ git clone https://github.com/liuderchi/chattium.git && cd chattium
$ docker run --rm -d \
  -p 22:22 -p 3000:3000 -p 3001:3001 \
  -v $PWD:/root/chattium \
  liuderchi/chattium-ubuntu16-node10-ssh:latest
```

2. Connect to the ssh server (password: `root`)

```bash
$ ssh -o UserKnownHostsFile=/dev/null root@localhost
```

## Deploy with [Now CLI](https://github.com/zeit/now-cli)

```sh
cd client && \
  yarun build && \
  rm build/static/js/*.map
cd ../ && now
```