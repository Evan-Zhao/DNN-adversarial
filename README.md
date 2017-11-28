# DNN Adversarial Examples Collection

This repo collects ideas on adversarial examples for DNN (deep neural networks), the procedures to reproduce them, and hopefully also the reproduced DNN and adversarial dataset set, so that study of misclassification in deep learning systems becomes easier.

## Source and Criterion on the Examples Collected

First, for a given task, there are (naturally) some DNNs that perform better and some that performs worse. Since we're working to reveal the corner cases for deep learning systems, having a collection of trivial DNNs are of less help. We prefer industrial-strength and state-of-the-art DL systems instead.

In practice, it turned out that most of the examples come from papers on *adversarial examples*. Accordingly, to replicate the result we often need DNNs *trained by ourselves* strictly following the proposal of these papers, and only in some cases, the papers refer to pre-trained environments that are ready to apply. 

Obtaining examples on industrial DL system failure is, put simply, impossible. DNNs used by commercial products are meant to be internal, and even reports on such failures are also not available. We've also gone through several [Google self-driving car monthly reports](https://static.googleusercontent.com/media/www.google.com/zh-CN//selfdrivingcar/files/reports/report-0916.pdf) trying to find accidents that involved technical details, but end up only with cases that can be readily blamed on human decision failure.

In addition, the [DeepXplore](https://dl.acm.org/citation.cfm?id=3132785) paper has already collected some examples -- mainly on image processing -- so we'll not spend too much time on this area. We do have some image-processing DNNs fooled by *another* kind of adversarial examples, and we'll see them later.

`TODO`: all examples below are supposed to be reproducible, and for most we've included an outline on how to reproduce them, but we'll need some time for that to be done. Some examples may not only require a properly trained DNN (the one to be attacked), but also an adversarial network or case-generating algorithms, so that will be some non-trivial work.

## General Idea on Adversarial Examples

Here you'll see some [interesting comments](image-process/explaining-adversarial.md) on the nature of adversarial attack and defence.

## Image Processing

Materials on this topic are contained under path `/image-process`.

For now we have 2 reproducible examples:

1. [Indirectly encoded images](image-process/indirectly-encoded-images.md): generates counter-examples for image DNN, but of a different kind from these generated by DeepXplore.

1. [Black-box attack](image-process/black-box-attack.md): generates cases for classifiers with unknown structure (blackbox), which applies to Amazon and Google ML services (and makes it more interesting).

The papers [[4]](https://arxiv.org/pdf/1412.6572.pdf) and [[5]](https://arxiv.org/pdf/1607.02533.pdf) also contains some examples that are more similar to these found in DeepXplore paper.

## Natural Language Processing (NLP)

Materials on this topic are contained under path `/nlp`.

Currently we have 1 reproducible example:

1. [Evaluating reading comprehension systems](nlp/eval-reading-system.md): generates perturbed query based on seed query for reading comprehension system. 

`TODO`: we have some other interesting unread papers on NLP, including: 

* [Adversarial Evaluation for Models of Natural Language](https://pdfs.semanticscholar.org/94a8/30c18aee5263a22bfc3cfde7f03e455f2312.pdf)

* [Adversarial Examples in NLP Contexts](https://nlp.stanford.edu/courses/cs224n/2015/reports/29.pdf)

## List of Paper Reference

Numbering of papers in subtopic files also follow this. Some paper may have local copy since we'll more frequently refer to them than others.

1. Anh Nguyen et al. "Deep Neural Networks are Easily Fooled: High Confidence Predictions for Unrecognizable Images." [local](image-process/dnn-fooling-1412.1897.pdf)/[arXiv link](https://arxiv.org/pdf/1412.1897.pdf)

1. Yangqing Jia et al. "Caffe: Convolutional Architecture for Fast Feature Embedding." [arXiv link](https://arxiv.org/pdf/1408.5093.pdf)

1. Nicolas Papernot et al. "Practical black-box attacks against deep learning systems using adversarial examples." [local](image-process/black-box-1602.02697.pdf)/[arXiv link](https://arxiv.org/pdf/1602.02697.pdf)

1. Ian J. Goodfellow et al. "Explaining and Harnessing Adversarial Examples." [arXiv link](https://arxiv.org/pdf/1412.6572.pdf)

1. Alexey Kurakin et al. "Adversarial Examples in the Physical World." [arXiv link](https://arxiv.org/pdf/1607.02533.pdf)

1. Robin Jia, Percy Liang. "Adversarial Examples for Evaluating Reading Comprehension Systems." [local](nlp/eval-reading-system-1707.07328.pdf)/[arXiv link](https://arxiv.org/pdf/1707.07328.pdf)