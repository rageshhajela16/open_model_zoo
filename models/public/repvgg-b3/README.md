# repvgg-b3

## Use Case and High-Level Description

RepVGG-B3 is a heavyweight RepVGG image classification model pre-trained on ImageNet dataset in 200 epochs. RepVGG is architecture of convolutional neural network, which has a VGG-like inference-time body and a structural re-parameterization technique. The 3x3 layers are arranged into five stages. RepVGG-B stages have 1, 4, 6, 16, 1 layers respectively. The layer width for these models is determined by uniform scaling the classic width setting of [64a, 128a, 256a, 512b]. RepVGG-B3 model has multipliers a = 3 and b = 5.

The model input is a blob that consists of a single image of `1, 3, 224, 224` in `RGB` order.

The model output is typical object classifier for the 1000 different classifications matching with those in the ImageNet database.

For details see [repository](https://github.com/DingXiaoH/RepVGG) and [paper](https://arxiv.org/abs/2101.03697).

## Specification

| Metric           | Value          |
| ---------------- | -------------- |
| Type             | Classification |
| GFLOPs           | 52.4407        |
| MParams          | 110.9609       |
| Source framework | PyTorch\*      |

## Accuracy

| Metric | Value  |
| ------ | ------ |
| Top 1  | 80.50% |
| Top 5  | 95.25% |

## Input

### Original model

Image, name - `input`,  shape - `1, 3, 224, 224`, format is `B, C, H, W`, where:

- `B` - batch size
- `C` - channel
- `H` - height
- `W` - width

Channel order is `RGB`.
Mean values - [123.675, 116.28, 103.53], scale values - [58.395, 57.12, 57.375].

### Converted model

Image, name - `input`,  shape - `1, 3, 224, 224`, format is `B, C, H, W`, where:

- `B` - batch size
- `C` - channel
- `H` - height
- `W` - width

Channel order is `BGR`.

## Output

### Original model

Object classifier according to ImageNet classes, name - `output`,  shape - `1, 1000`, output data format is `B, C`, where:

- `B` - batch size
- `C` - predicted probabilities for each class in logits format

### Converted model

Object classifier according to ImageNet classes, name - `output`,  shape - `1, 1000`, output data format is `B, C`, where:

- `B` - batch size
- `C` - predicted probabilities for each class in logits format

## Download a Model and Convert it into Inference Engine Format

You can download models and if necessary convert them into Inference Engine format using the [Model Downloader and other automation tools](../../../tools/model_tools/README.md) as shown in the examples below.

An example of using the Model Downloader:
```
omz_downloader --name <model_name>
```

An example of using the Model Converter:
```
omz_converter --name <model_name>
```

## Demo usage

The model can be used in the following demos provided by the Open Model Zoo to show its capabilities:

* [Classification Benchmark C++ Demo](../../../demos/classification_benchmark_demo/cpp/README.md)
* [Classification Python\* Demo](../../../demos/classification_demo/python/README.md)

## Legal Information

The original model is released under the following [license](https://raw.githubusercontent.com/DingXiaoH/RepVGG/main/LICENSE):

```
MIT License

Copyright (c) 2020 DingXiaoH

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
