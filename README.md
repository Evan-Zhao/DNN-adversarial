# Collection of ML System Misclassification

(Update: apart from adversarial examples, now we also have reports for real-world DNN errors that have actually occurred, methods for generating more "realworld-looking" counterexamples, and others, so we changed the title a bit.)

This repo collects ideas on misclassification examples for ML (machine learning) systems, including those occurred and those could be manually triggered. For some, we'll also include some attempt to  reproduce and spot them. This collection prefers industrial-strength and state-of-the-art ML systems.

We'll try to collect examples from as many fields (image processing, reinforcement learning, natural language processing, etc.) as possible. 

The [DeepXplore](https://dl.acm.org/citation.cfm?id=3132785) paper has already collected some examples -- mainly on image processing -- so we'll not spend too much time on this area. We do have some image-processing DNNs fooled by *another* kind of adversarial examples, and we'll see them later.

[CleverHans](https://github.com/tensorflow/cleverhans) is a library for benchmarking ML systems, testing their performance against adversarial examples. If we wish to reproduce certain misclassification of ML system, this library may automate most of work for us.

## [Real-world Accidents Involving ML Systems](./ML-accidents.md)

- Self-driving car accidents

- Stereotypical and biased AI (racism, anti-feminism, etc.)

## Generating Counterexamples

(Materials under [`/generative`](generative/))

Generating counterexamples for a given ML system can provide insight on where it could go wrong. With regard to the examples generated, these methods can be classified into the following categories.

### Adversarial methods

Adversarial methods perturb a given (valid) input by small amount so that it's still the same under human perception, but classified differently by machine. [Here](generative/explaining-adversarial.md) are details on this method.

Adversarials are particularly useful for attacking ML systems since the variation is made difficult to perceive by human. Accordingly, some defensive methods are designed to prevent such attack. [This](generative/ML-attack-defence.md) introduces some attack and defence approaches relevant to ML systems.

### Direct encoding

Direct encoding pick up a input directly from the input space which usually is unrecognizable, but the target DNN is confident that it belongs to certain class. 

This category is rare. The paper [[1]](papers/dnn-fooling-1412.1897.pdf) is representative on this method; the term "direct encoding" is also coined is this paper. For an explanation of this category, see this [review](./review/dnn-fooling.md).

### Indirect encoding

Indirect encoding instead pick a value from a *latent space*, and generatively map it to the input space (typically using GAN, generative adversarial network). The generated input may be valid or invalid but resembles a valid input, while the target DNN will be fooled.

The paper [[1]](papers/dnn-fooling-1412.1897.pdf) also apply indirect encoding to generate unnatural images containing certain patterns that will more effectively confuse DNNs. 

[[11]](https://arxiv.org/pdf/1710.11342.pdf) purposes instead that valid and *natural* images could be generated which confuse DNNs to misclassify them just like adversarial examples, but more resembles real-world inputs.

---

With regard to the access required, the methods can be again classified into these categories:

`TODO`: fill in this part with material.

1. White-box method. They require full knowledge to the ML systems being studied, which in the case of DNN will be the structure and weights of network.

1. Black-box method. They could work with ML systems with only input and output accessible. 

    Black-box methods differ in "opacity" of the box. For example, in classification model with confidence output, while some methods require access to the confidence value, some only require classification result. Certain methods does not need the ability to feed input and receive feedback one-on-one, but could instead process input and output datasets and infer correspondence. 

`TODO`: fill the categories below.
## Image Processing

(Materials under [`/image-process`](image-process/)).

For now we have 2 reproducible examples:

1. [Indirectly encoded images](papers/indirectly-encoded-images.md): generates counter-examples for image DNN, but of a different kind from these generated by DeepXplore.

2. [Black-box attack](papers/black-box-attack.md): generates cases for classifiers with unknown structure (blackbox), which applies to Amazon and Google ML services (and makes it more interesting).

The papers [[4]](https://arxiv.org/pdf/1412.6572.pdf) and [[5]](https://arxiv.org/pdf/1607.02533.pdf) also contains some examples that are more similar to these found in DeepXplore paper.

## Natural Language Processing (NLP)

Materials on this topic are contained under path `/nlp`.

Currently we have 1 reproducible example:

1. [Evaluating reading comprehension systems](papers/eval-reading-system.md): generates perturbed query based on seed query for reading comprehension system. 

`TODO`: we have some other interesting unread papers on NLP, including: 

* [Adversarial Evaluation for Models of Natural Language](https://pdfs.semanticscholar.org/94a8/30c18aee5263a22bfc3cfde7f03e455f2312.pdf)

* [Adversarial Examples in NLP Contexts](https://nlp.stanford.edu/courses/cs224n/2015/reports/29.pdf)

## Reinforcement Learning