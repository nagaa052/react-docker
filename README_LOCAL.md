# Dockerfile
## Image作成
docker image build -t react:app .

## コンテナ起動
docker run -it --name react -p 3000:3000 -p 35729:35729 -v $(pwd):/app react:app

## コンテナ起動(スナップショットから)
docker start react

## 停止
docker stop react

## ssh
docker exec -it react bash

## package 追加
docker exec react bash -c "cd /app && yarn add material-ui"
docker exec react bash -c "cd /app && yarn add react-tap-event-plugin"


# docker-compose
## Build & 起動
docker-compose up -d --build

## package 追加
docker-compose run node yarn add react-router-dom
