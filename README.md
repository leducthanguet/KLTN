















# PyContinual (An Easy and Extendible Framework for Continual Learning)



## Easy to Use

You can sumply change the `baseline`, `backbone` and `task`, and then ready to go.
Here is an example:
```python
	python run.py \  
	--bert_model 'bert-base-uncased' \  
	--backbone bert_adapter \ #or other backbones (bert, w2v...)  
	--baseline ctr \  #or other avilable baselines (classic, ewc...)
	--task asc \  #or other avilable task/dataset (dsc, newsgroup...)
	--eval_batch_size 128 \  
	--train_batch_size 32 \  
	--scenario til_classification \  #or other avilable scenario (dil_classification...)
	--idrandom 0  \ #which random sequence to use
	--use_predefine_args #use pre-defined arguments
```

## Easy to Extend

You only need to write  your own `./dataloader`, `./networks` and `./approaches`. You are ready to [go](https://github.com/ZixuanKe/PyContinual/blob/main/docs/run_own.md)!

## Performance

<p align="center">
    <br>
    <a href="https://github.com/ZixuanKe/PyContinual">
        <img src="https://github.com/ZixuanKe/PyContinual/blob/main/docs/benchmarks.png" width="500"/>
    </a>    
    <br>
<p>


## Introduction
Recently, continual learning approaches have drawn more and more attention. This repo contains pytorch implementation of a set of (improved) SoTA methods using the same training and evaluation pipeline.

This repository contains the code for the following papers:
*  [Achieving Forgetting Prevention and Knowledge Transfer in Continual Learning](https://proceedings.neurips.cc/paper/2021/hash/bcd0049c35799cdf57d06eaf2eb3cff6-Abstract.html), Zixuan Ke, [Bing Liu](https://www.cs.uic.edu/~liub/), Nianzu Ma, [Hu Xu](https://howardhsu.github.io/) and [Lei Shu](https://leishu02.github.io/), NeurIPS 2021
*  [CLASSIC: Continual and Contrastive Learning of Aspect Sentiment Classification Tasks](https://aclanthology.org/2021.emnlp-main.550/), Zixuan Ke, [Bing Liu](https://www.cs.uic.edu/~liub/), [Hu Xu](https://howardhsu.github.io/) and [Lei Shu](https://leishu02.github.io/), EMNLP 2021
*  [Adapting BERT for Continual Learning of a Sequence of Aspect Sentiment Classification Tasks](https://www.aclweb.org/anthology/2021.naacl-main.378.pdf), Zixuan Ke, [Hu Xu](https://howardhsu.github.io/) and [Bing Liu](https://www.cs.uic.edu/~liub/), NAACL 2021
* [Continual Learning of a Mixed Sequence of Similar and Dissimilar Tasks](https://proceedings.neurips.cc/paper/2020/file/d7488039246a405baf6a7cbc3613a56f-Paper.pdf), Zixuan Ke, [Bing Liu](https://www.cs.uic.edu/~liub/) and [Xingchang Huang](https://people.mpi-inf.mpg.de/~xhuang/), NeurIPS 2020 (if you only care about this model, you can also check [CAT](https://github.com/ZixuanKe/CAT))
* [Continual Learning with Knowledge Transfer for Sentiment Classification](https://www.cs.uic.edu/~liub/publications/ECML-PKDD-2020.pdf), Zixuan Ke, [Bing Liu](https://www.cs.uic.edu/~liub/), [Hao Wang](https://cshaowang.github.io/) and [Lei Shu](https://leishu02.github.io/), ECML-PKDD 2020 (if you only care about this model, you can also check [LifelongSentClass](https://github.com/ZixuanKe/LifelongSentClass))
* **[40+](https://github.com/ZixuanKe/PyContinual/blob/master/docs/baselines.md)** baselines and variants (and keeps "continually" growing!)


## Features
* **Datasets**: It currently supports **Language Datasets** (Document/Sentence/Aspect Sentiment Classification, Natural Language Inference, Topic Classification) and **Image Datasets** (CelebA, CIFAR10, CIFAR100, FashionMNIST, F-EMNIST, MNIST, VLCS)
* **Scenarios**: It currently supports **Task Incremental Learning** and **Domain Incremental Learning**
* **Training Modes**: It currently supports single-GPU. You can also change it to multi-node distributed training and the mixed precision training.

## Architecture
`./res`: all results saved in this folder.  
`./dat`: processed data  
`./data`: raw data
`./dataloader`: contained dataloader for different data
`./approaches`: code for training  
`./networks`: code for network architecture  
`./data_seq`:  some reference sequences (e.g. asc_random)
`./tools`: code for preparing the data

## Setup
* If you want to run the existing systems, please see [run_exist.md](https://github.com/ZixuanKe/PyContinual/blob/master/docs/run_exist.md)
* If you want to expand the framework with your own model, please see  [run_own.md](https://github.com/ZixuanKe/PyContinual/blob/master/docs/run_own.md)
* If you want to see the full list of baselines and variants, please see [baselines.md](https://github.com/ZixuanKe/PyContinual/blob/master/docs/baselines.md)


## Reference
If using this code, parts of it, or developments from it, please consider cite the references bellow.

	@inproceedings{ke2021achieve,
	  title={Achieving Forgetting Prevention and Knowledge Transfer in Continual Learning},
	  author={Ke, Zixuan and Liu, Bing and Ma, Nianzu and Xu, Hu, and Lei Shu},
	  booktitle={NeurIPS},
	  year={2021}
	}
	
	@inproceedings{ke2021contrast,
	  title={CLASSIC: Continual and Contrastive Learning of Aspect Sentiment Classification Tasks},
	  author={Ke, Zixuan and Liu, Bing and Xu, Hu, and Lei Shu},
	  booktitle={EMNLP},
	  year={2021}
	}

	@inproceedings{ke2021adapting,
	  title={Adapting BERT for Continual Learning of a Sequence of Aspect Sentiment Classification Tasks},
	  author={Ke, Zixuan and Xu, Hu and Liu, Bing},
	  booktitle={Proceedings of the 2021 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies},
	  pages={4746--4755},
	  year={2021}
	}

    @inproceedings{ke2020continualmixed,
    author= {Ke, Zixuan and Liu, Bing and Huang, Xingchang},
    title= {Continual Learning of a Mixed Sequence of Similar and Dissimilar Tasks},
    booktitle = {Advances in Neural Information Processing Systems},
    volume={33},
    year = {2020}}

	@inproceedings{ke2020continual,
	author= {Zixuan Ke and Bing Liu and Hao Wang and Lei Shu},
	title= {Continual Learning with Knowledge Transfer for Sentiment Classification},
	booktitle = {ECML-PKDD},
	year = {2020}}

    
## Contact


Please drop an email to [Zixuan Ke](mailto:zke4@uic.edu), [Xingchang Huang](mailto:huangxch3@gmail.com) or [Nianzu Ma](mailto:jingyima005@gmail.com) if you have any questions regarding to the code. We thank [Bing Liu](https://www.cs.uic.edu/~liub/), [Hu Xu](https://howardhsu.github.io/) and [Lei Shu](https://leishu02.github.io/) for their valuable comments and opinioins.



