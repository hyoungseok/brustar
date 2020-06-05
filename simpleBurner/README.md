# simple burner
simplify overall code
+ docker == 18.09.1
+ libTorch == 1.5.0 (cpu, linux)
+ independent with `.pth` file
+ please keep package name as `burner` in your external code
+ to manage batch / output dimension, see `src/Model.cpp`

## build image
excute below uner `simpleBurner` directory to create `libModel.so` file under `/home/brusta`
```
cd simpleBurner
docker build -t brusta -f Dockerfile-brusta .
```

## copy file from temporary container of above image ([link](https://www.youtube.com/watch?v=KtujZdV3G1E))
1. run temporary docker container
```
docker run -it --rm brusta bash
```
2. copy container hostname and copy `libModel.so`
```
docker cp [container hostname]:/home/brusta/libModel.so [destination path]
```
3. quit temporary container

