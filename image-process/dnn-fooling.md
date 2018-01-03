# [Deep Neural Networks are Easily Fooled: High Confidence Predictions for Unrecognizable Images](https://arxiv.org/pdf/1412.1897.pdf)

###### Anh Nguyen, Jason Yosinski, Jeff Clune

---

### What is the Problem?

Despite the near-human-level performance that DNNs have shown in image processing, large differences exist between computer and human vision: changing an image in imperceptable way to human could result in a DNN labeling the image as something else entirely. We say that under certain circumstances the DNNs are easily "fooled."

### Summary

Nguyen et al. apply evolutionary algorithms (EA) and direct/indirect image encoding to get invalid images that the DNN believes is valid and belong to certain category with high confidence. Image generation is driven by EA, and encoders produce the images from EA result. Both methods quite easily "fool" the MNIST and ImageNet DNNs, contradicting the authors' original hypotheses.

### Key Insights

The generated images contains patterns that resembles the target category. These artifacts provide insights in what a DNN is looking at when it classifies an image to a certain category. 

For example, the following figure is a part of Fig. 8 in original paper, which cheats the image classifier to believe this is a school bus. As far as the classifier is concerned, a school bus is alternating yellow and black lines, but does not need to have a windshield or wheels.

![CPNN-fool-example](dnn-fooling-fig-8.jpg)

### Notable Design Details/Strengths

MAP-Elites method is deployed as modification of evolutional algorithm so that optimization on many target classes simutaneously becomes computationally effective.

### Limitations/Weaknesses

The procedure relies on knowledge of the confidence level output (if the system is a classifier), which can be seen in the statement (section 2.2): 

    > ... fitness function, which in these experiments is the highest prediction value a DNN makes for that image belonging to a class.

(The paper [[11]](https://arxiv.org/pdf/1710.11342.pdf) addresses this problem.)

### Summary of Key Results

### Open Questions

