# googlenet-v1

## Use Case and High-Level Description

The `googlenet-v1` model is the first of the [Inception](https://arxiv.org/abs/1602.07261) family of models designed to perform image classification. Like the other Inception models, the `googlenet-v1` model has been pre-trained on the ImageNet image database. For details about this family of models, check out the paper.

The model input is a blob that consists of a single image of `1, 3, 224, 224` in `BGR` order. The BGR mean values need to be subtracted as follows: [104.0, 117.0, 123.0] before passing the image blob into the network.

The model output for `googlenet-v1` is the typical object classifier output for the 1000 different classifications matching those in the ImageNet database.

## Specification

| Metric            | Value         |
|-------------------|---------------|
| Type              | Classification|
| GFLOPs            | 3.266         |
| MParams           | 6.999         |
| Source framework  | Caffe\*       |

## Accuracy

| Metric | Value  |
| ------ | ------ |
| Top 1  | 68.928%|
| Top 5  | 89.144%|

See [the original repository](https://github.com/BVLC/caffe/tree/master/models/bvlc_googlenet).

## Input

### Original model

Image, name - `data`,  shape - `1, 3, 224, 224`, format is `B, C, H, W`, where:

- `B` - batch size
- `C` - channel
- `H` - height
- `W` - width

Channel order is `BGR`.
Mean values - [104.0, 117.0, 123.0]

### Converted model

Image, name - `data`,  shape - `1, 3, 224, 224`, format is `B, C, H, W`, where:

- `B` - batch size
- `C` - channel
- `H` - height
- `W` - width

Channel order is `BGR`

## Output

### Original model

Object classifier according to ImageNet classes, name - `prob`,  shape - `1, 1000`, output data format is `B, C`, where:

- `B` - batch size
- `C` - predicted probabilities for each class in [0, 1] range

### Converted model

Object classifier according to ImageNet classes, name - `prob`,  shape - `1, 1000`, output data format is `B, C`, where:

- `B` - batch size
- `C` - predicted probabilities for each class in [0, 1] range

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

The original model is distributed under the following
[license](https://raw.githubusercontent.com/BVLC/caffe/master/models/bvlc_googlenet/readme.md):

```
This model is released for unrestricted use.
```
