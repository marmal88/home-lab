# Nvidia Triton Inference Server

This application is meant to be run on the Nvidia Jetson Orin Nano edge device. The application consist of 2 parts the triton inference server as well as an external

```
# apply both the deployment and service
k apply -f triton-deploy.yaml
k apply -f triton-server.yaml
```


```
# load the model
curl -X POST http://192.168.50.201:8000/v2/repository/models/densenet_onnx/load
# Unload the model
curl -X POST http://192.168.50.201:8000/v2/repository/models/densenet_onnx/unload
```

```
docker run -it --rm nvcr.io/nvidia/tritonserver:24.07-py3-sdk \
/workspace/install/bin/image_client \
-i grpc \
-u 192.168.50.201:8001 \
-m densenet_onnx \
-c 3 \
-s INCEPTION \
/workspace/images/mug.jpg
```
