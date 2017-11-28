(This is a topic in [README.md](../README.md).)

# Explaining Adversarial Examples

Nguyen et al. comment in the paper that generating adversarial examples is easy: train a DNN with an amount of adversarial examples, and time after time they are able to generate new such examples. Other authors show that adversarial examples could survive across differently structured DNNs trained with the same dataset [[4]](https://arxiv.org/pdf/1412.6572.pdf), and even after photo transformations [[5]](https://arxiv.org/pdf/1607.02533.pdf).

Accordingly, defence for DNN is difficult and tends to fail; Papernot et al. invalidated defence based on gradient masking in [[3]](https://arxiv.org/pdf/1602.02697.pdf).

(We could also consider what to do after we successfully find adversarial examples, because fixing a DNN turns out to be a non-trivial problem.)

Goodfellow et al. explain that these phenomenon have to do with *linear behavior in a high-dimensional space*. The basic idea is that, there exists some *directions* in the space that "aligns most closely with weights of a DNN (on a certain output)," and when the input contains a component in that direction, the classification is forced to be the corresponding output. Details at [[4]](https://arxiv.org/pdf/1412.6572.pdf).