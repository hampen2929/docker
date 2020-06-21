# docker

## GPU

```
cd docker/gpu/
docker build -t dev_image_gpu .
```

```
docker run --runtime=nvidia -it \
--name dev_gpu \
--rm \
-e DISPLAY=$DISPLAY \
-v /tmp/.X11-unix:/tmp/.X11-unix \
-v $HOME/workspace:/workspace \
-p 8888:8888 \
dev_image_gpu \
/bin/bash

docker start run dev_gpu
docker exec -it dev_gpu /bin/bash
```

## CPU

### Build

```
cd docker/cpu/
docker build -t dev_image_cpu ./
```

```
docker run -it \
--rm \
--name dev_cpu \
-e DISPLAY=$DISPLAY \
-v /tmp/.X11-unix:/tmp/.X11-unix \
-v $HOME/workspace:/workspace \
-p 8888:8888 \
dev_image_cpu \
/bin/bash

docker start run dev_cpu
docker exec -it dev_cpu /bin/bash
```
