# docker

## GPU

### Build

```
cd docker/base/
docker build -t base_image_gpu .

cd ../dev
docker build -t dev_image_gpu .
```

docker run --runtime=nvidia -it \
--name dev_gpu \
-e DISPLAY=$DISPLAY \
-v /tmp/.X11-unix:/tmp/.X11-unix \
-v $HOME/workspace:/workspace \
-p 8888:8888 \
dev_image_gpu \
/bin/bash

docker start run dev_gpu
docker exec -it dev_gpu bash

## CPU

### Build

```
cd docker/cpu/base/
docker build -t base_image_cpu .

cd ../dev
docker build -t dev_image_cpu ./
```

docker run --runtime=nvidia -it \
--name dev_cpu \
-e DISPLAY=$DISPLAY \
-v /tmp/.X11-unix:/tmp/.X11-unix \
-v $HOME/workspace:/workspace \
-p 8888:8888 \
dev_image_cpu \
/bin/bash

docker start run dev_cpu
docker exec -it dev_cpu bash

