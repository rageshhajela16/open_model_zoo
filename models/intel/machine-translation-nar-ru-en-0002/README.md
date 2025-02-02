# machine-translation-nar-ru-en-0002

## Use Case and High-Level Description

This is a Russian-English machine translation model based on non-autoregressive Transformer topology.

Tokenization occurs using the SentencePieceBPETokenizer (see the demo code for implementation details) and the enclosed tokenizer_src and tokenizer_tgt folders.

## Specification

| Metric            | Value                 |
|-------------------|-----------------------|
| GOps              | 23.17                 |
| MParams           | 69.29                 |
| Source framework  | PyTorch\*             |

## Accuracy

The quality metrics were calculated on the wmt19-ru-en dataset ("test" split in lower case).

| Metric                    | Value         |
|---------------------------|---------------|
| BLEU                      |        23.1 % |

## Input

name: `tokens`
shape: `1, 192`
description: sequence of tokens (integer values) representing the tokenized sentence.
The sequence structure is as follows (`<s>`, `</s>` and `<pad>` should be replaced by corresponding token IDs as specified by the dictionary):
`<s>` + *tokenized sentence* + `</s>` + (`<pad>` tokens to pad to the maximum sequence length of 192)

## Output

name: `pred`
shape: `1, 192`
description: sequence of tokens (integer values) representing the tokenized translation.
The sequence structure is as follows (`<s>`, `</s>` and `<pad>` should be replaced by corresponding token IDs as specified by the dictionary):
`<s>` + *tokenized sentence* + `</s>` + (`<pad>` tokens to pad to the maximum sequence length of 192)

## Demo usage

The model can be used in the following demos provided by the Open Model Zoo to show its capabilities:

* [Machine Translation Python\* Demo](../../../demos/machine_translation_demo/python/README.md)

## Legal Information
[*] Other names and brands may be claimed as the property of others.
