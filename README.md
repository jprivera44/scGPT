# scGPT

This is the official codebase for **scGPT: Towards Building a Foundation Model for Single-Cell Multi-omics Using Generative AI**.

[Preprint](https://www.biorxiv.org/content/10.1101/2023.04.30.538439)

[Documentation](https://scgpt.readthedocs.io/en/latest/)

!UPDATE: We have released several new pretrained scGPT checkpoints. Please see the [Pretrained scGPT checkpoints](#pretrained-scGPT-checkpoints) section for more details.

## Installation

scGPT is available on PyPI. To install scGPT, run the following command:

```bash
$ pip install scgpt
```

[Optional] We recommend using [wandb](https://wandb.ai/) for logging and visualization.

```bash
$ pip install wandb
```

For developing, we are using the [Poetry](https://python-poetry.org/) package manager. To install Poetry, follow the instructions [here](https://python-poetry.org/docs/#installation).

```bash
$ git clone this-repo-url
$ cd scGPT
$ poetry install
```

**Note**: The `flash-attn` dependency usually requires specific GPU and CUDA version. If you encounter any issues, please refer to the [flash-attn](https://github.com/HazyResearch/flash-attention/tree/main) repository for installation instructions. For now, May 2023, we recommend using CUDA 11.7 and flash-attn<1.0.5 due to various issues reported about installing new versions of flash-attn.

## Pretrained scGPT Model Zoo

Here is the list of pretrained models. Please find the links for downloading the checkpoint folders. We recommend using the `whole-human` model for most applications by default. If your fine-tuning dataset shares similar cell type context with the training data of the organ-specific models, these models can usually demonstrate competitive performance as well.

| Model name                | Description                                             | Download                                                                                     |
| :------------------------ | :------------------------------------------------------ | :------------------------------------------------------------------------------------------- |
| whole-human (recommended) | Pretrained on 33 million normal human cells.            | [link](https://drive.google.com/drive/folders/1oWh_-ZRdhtoGQ2Fw24HP41FgLoomVo-y?usp=sharing) |
| brain                     | Pretrained on 13.2 million brain cells.                 | [link](https://drive.google.com/drive/folders/1vf1ijfQSk7rGdDGpBntR5bi5g6gNt-Gx?usp=sharing) |
| blood                     | Pretrained on 10.3 million blood and bone marrow cells. | [link](https://drive.google.com/drive/folders/1kkug5C7NjvXIwQGGaGoqXTk_Lb_pDrBU?usp=sharing) |
| heart                     | Pretrained on 1.8 million heart cells                   | [link](https://drive.google.com/drive/folders/1GcgXrd7apn6y4Ze_iSCncskX3UsWPY2r?usp=sharing) |
| lung                      | Pretrained on 2.1 million lung cells                    | [link](https://drive.google.com/drive/folders/16A1DJ30PT6bodt4bWLa4hpS7gbWZQFBG?usp=sharing) |
| kidney                    | Pretrained on 814 thousand kidney cells                 | [link](https://drive.google.com/drive/folders/1S-1AR65DF120kNFpEbWCvRHPhpkGK3kK?usp=sharing) |
| pan-cancer                | Pretrained on 5.7 million cells of various cancer types | [link](https://drive.google.com/drive/folders/13QzLHilYUd0v3HTwa_9n4G4yEF-hdkqa?usp=sharing) |

## Fine-tune scGPT for scRNA-seq integration

Please see our example code in [examples/finetune_integration.py](examples/finetune_integration.py). By default, the script assumes the scGPT checkpoint folder stored in the `examples/save` directory.

## To-do-list

- [x] Upload the pretrained model checkpoint
- [x] Publish to pypi
- [ ] Provide the pretraining code with generative attention masking
- [ ] Finetuning examples for multi-omics integration, cell tyep annotation, perturbation prediction, cell generation
- [x] Example code for Gene Regulatory Network analysis
- [x] Documentation website with readthedocs
- [ ] Bump up to pytorch 2.0
- [x] New pretraining on larger datasets
- [ ] Reference mapping example
- [ ] Publish to huggingface model hub

## Contributing

We greatly welcome contributions to scGPT. Please submit a pull request if you have any ideas or bug fixes. We also welcome any issues you encounter while using scGPT.

## Acknowledgements

We sincerely thank the authors of following open-source projects:

- [flash-attention](https://github.com/HazyResearch/flash-attention)
- [scanpy](https://github.com/scverse/scanpy)
- [scvi-tools](https://github.com/scverse/scvi-tools)
- [scib](https://github.com/theislab/scib)
- [datasets](https://github.com/huggingface/datasets)
- [transformers](https://github.com/huggingface/transformers)

## Citing scGPT

```bibtex
@article{cui2023scGPT,
title={scGPT: Towards Building a Foundation Model for Single-Cell Multi-omics Using Generative AI},
author={Cui, Haotian and Wang, Chloe and Maan, Hassaan and Pang, Kuan and Luo, Fengning and Wang, Bo},
journal={bioRxiv},
year={2023},
publisher={Cold Spring Harbor Laboratory}
}
```
