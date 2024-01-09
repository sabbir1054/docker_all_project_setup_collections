# DOCKER

---

**Add ubuntu in docker**

```
 docker pull ubuntu
```

**Start ubuntu**

```
docker run -it ubuntu
```

---

**Build an Image**

```
docker build -t hello-docker .
```

**Check images list**

```
docker images
```

**Run Docker image**

```
docker run hello-docker
```

**List of all current active running Containers**

```
docker ps
```

**List of all active or inactive container**

```
docker ps -a
```

**Stop Specific Docker container**

```
docker stop container_name

```

> [!TIP]
> we can use container_name/id/first 3 character

**Remove Specific container**

```
docker rm container_id
```

> [!IMPORTANT]  
> We can not remove running container normally. For this we should use --force.

**Remove all inactive container**

```
docker container prune
```

---

## React Project

- Make react project by using vite
- Make dockerfile and .docker ignore files

**Build React Docker Image**

```
docker build -t react-docker-setup
```

**Run React Docker Image**

```
docker run react-docker-setup
```

> [!CAUTION]
> It not run in localhost of my computer because docker not expose the port.

**Now mapped Port of docker and local machine**

```
docker run -p 5173:5173 react-docker-setup
```

> [!CAUTION]
> After mapped port i should change the package.json file add --host in dev command. Then again run the image

> [!NOTE]  
> By this way if we change something in our code it not update in our localhost automatically
> we need every time rebuild it and run it.

**For automatically build and update**

```
docker run -p 5173:5173 -v "$(pwd):/app/" -v /app/node_modules react-docker-setup
```

---

## Now use docker init that made developer life easy

```
docker init
```

**Run docker compose**

```
docker compose up
```

**Auto start dev Docker watch**

```
docker compose watch
```
