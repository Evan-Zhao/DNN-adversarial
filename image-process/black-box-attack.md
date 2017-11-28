(This is a topic in [README.md](../README.md).)

# Black-box Attack

We're excluding a bunch of examples similar to these DeepXplore covered. This one is also similar in the type of cases it generates, but the interesting thing is one could actually go to *Amazon ML platform*, or *Google Cloud Prediction API*, train a model just by feeding data, and figure out adversarial examples simply by looking at the output. 

Purposed by Papernot et al., this black-box method uses a DNN to simulate an oracle. [[3]](black-box-1602.02697.pdf)

## Reproduction

First, we'll need a data set for the DNN to work on. The Papernot paper uses a unspecified CSV version of MNIST dataset. Other MNIST dataset should be the same in effect as long as it is correct, so we picked another set from [https://pjreddie.com/projects/mnist-in-csv/](https://pjreddie.com/projects/mnist-in-csv/) and store it in `/image-process/MNIST`. Now we have a train set and a test set.

Locate [Amazon AI service](https://aws.amazon.com/machine-learning) or [Google Cloud Prediction API](https://cloud.google.com/prediction/). Note that the latter will be shut down on April 30, 2018. 

Train the model by simply submitting CSV. The output will be feed back given some query. Given input and output of our blackbox model, the paper provides detailed procedures for attacking this model; however, to the best of our knowledge, there is no implementation of the process described by the paper. 

Basically, two parts of work needs to be done: generating a DNN imitating the *oracle* (our trained model) as described in section 4.1, and then generate adversarial examples for it according to 4.2. There will be a large amount of work.
