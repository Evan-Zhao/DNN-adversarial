# [Adversarial Examples for Evaluating Reading Comprehension Systems](https://arxiv.org/pdf/1707.07328.pdf)

###### Robin Jia, Percy Liang

---

### What is the Problem?

Reading comprehension systems are capable of reading certain text and answer some question based on the information in the text, yet the extent to which these systems truly understand language remains unclear. It is hoped that by creating adversarial examples, the limitation of current reading systems are better understood.

### Summary

Two types of variations are applied to the information text under the premise that the answer to the question is preserved. The resulted text drastically decreases the score of reading system without changing the answer of misleading human, implying that the tested models do not understand language precisely enough.

### Key Insights

Contrary to the case in computer vision, even small perturbations in text does not usually preserve its semantic. Instead of trying to preserve the semantics of text (paraphrasing) which is challenging, it is also a valid test to alter the semantics and expect the model to view them differently.

### Notable Design Details/Strengths

The two types of transformations are `AddAny` which appends several random words to the text, and `AddSent` which appends a sentence semantically altered from the question itself (to ensure that the resulted sentence *does not* answer the question). It is thus apparent that these transformations will never change the answer to the question.

### Limitations/Weaknesses

- The procedure has only weak ability to guarantee syntactic correctness of the sentence appended because it relies on 50 fixed syntax rules; checking is instead performed by crowdworkers.

- Generating fake answers of the same "type" as original answer requires a POS tag for original answer *and* fake answer.

### Summary of Key Results

Current models are not comprehending language well enough. Across the 16 models tested, only using `AddSent` transformation reduces the average score from 75% to 36%, while introducing `AddAny` further reduces the score to 7%. 

### Open Questions
