# [Generating Natural Adversarial Examples](https://arxiv.org/pdf/1710.11342.pdf)

###### Zhengli Zhao, Dheeru Dua, Sameer Singh

---

### What is the Problem?

Recent works on adversarial examples of DNNs produce malicious perturbations that are often unnatural, not semantically meaningful, and not applicable to complicated domains such as language. 

### Summary

The procedure performs search in a *latent* space, namely a dense and continuous representation of data, instead of the flat input space. A generator and an inverter translate back and forth between latent space and input space, ensuring that examples generated cheats target DNN (in input space) and meanwhile are near to training data (in latent space).

### Key Insights

- Latent space can be *learned* from training set by training the generator and invertor as generative adversarial networks (GANs). 

- The scale of minimal perturbation needed in latent space can be used as a measure of robustness of the classifier being attacked.

### Notable Design Details/Strengths

The *machine translation* task is transformed into a binary classification problem using a designated probing function. In this case: whether an additional active verb in English sentence is correctly translated in German output.

### Limitations/Weaknesses

- The search algorithm is much less efffective compared to graident methods that is generally used in other adversary methods. Graident methods do not port trivially to the procedures in this paper because graidents in input spaces cannot easily translate to that in latent space.

    (The author group is "interested in exploring more efficient search methods later.")

### Summary of Key Results

- The proposed method is effective for generating natural adversarial examples in both continuous (e.g. image) and discrete (e.g. text) input space.

- The minimal offset distance of adversarial examples in latent space is a meaningful metric for robustness of DNN. This distance increases with test accuracy of DNN being tested under MNIST settings.

### Open Questions

