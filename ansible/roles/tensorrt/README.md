# tensorrt

This role installs TensorRT and cuDNN following [this page](https://docs.nvidia.com/deeplearning/tensorrt/install-guide/index.html#installing).

## Inputs

| Name             | Required | Description              |
| ---------------- | -------- | ------------------------ |
| cudnn_version    | true     | The version of cuDNN.    |
| tensorrt_version | true     | The version of TensorRT. |

## Manual Installation

For Universe, the `cudnn_version` and `tensorrt_version` variable can also be found in:
[../../playbooks/universe.yaml](../../playbooks/universe.yaml)

```bash
# Taken from: https://docs.nvidia.com/deeplearning/tensorrt/install-guide/index.html#installing

cudnn_version="8.2.2.26-1+cuda11.4"
sudo apt-get install libcudnn8=${cudnn_version} libcudnn8-dev=${cudnn_version}
sudo apt-mark hold libcudnn8 libcudnn8-dev

tensorrt_version="8.2.2-1+cuda11.4"
sudo apt-get install libnvinfer8=${tensorrt_version} libnvonnxparsers8=${tensorrt_version} libnvparsers8=${tensorrt_version} libnvinfer-plugin8=${tensorrt_version} libnvinfer-dev=${tensorrt_version} libnvonnxparsers-dev=${tensorrt_version} libnvparsers-dev=${tensorrt_version} libnvinfer-plugin-dev=${tensorrt_version} python3-libnvinfer=${tensorrt_version}
sudo apt-mark hold libnvinfer8 libnvonnxparsers8 libnvparsers8 libnvinfer-plugin8 libnvinfer-dev libnvonnxparsers-dev libnvparsers-dev libnvinfer-plugin-dev python3-libnvinfer
```
