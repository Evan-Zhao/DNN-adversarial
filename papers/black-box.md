# [Practical Black-Box Attacks against Machine Learning](https://arxiv.org/pdf/1602.02697.pdf)

###### Nicolas Papernot, Patrick McDaniel, Ian Goodfellow, Somesh Jha, Z. Berkay Celik, Ananthram Swami

---

### What is the Problem?

Previous work on the attack of machine learning systems, though successfully shown vulnerability of ML systems, require knowledge of either the model internals or its training data. These methods invalidates when such information is impossible to obtain.

### Summary

Papernot et al. introduce the first practical demonstration of an attacker controlling a remotely hosted DNN, without knowledge of its structure or training set. Their black-box adversary builds a DNN locally by watching input and output of remote ML system, and generates attack targeting local DNN. The resulting attacks are proven effective to remote ML system as well.

### Key Insights

ML systems that respond similarly to the same input tend to have similar blind spots, even regardless of system type and structure. In many cases, adversarial examples that bring down one classifier easily extends to other classifiers.

### Notable Design Details/Strengths

### Limitations/Weaknesses

### Summary of Key Results

### Open Questions

