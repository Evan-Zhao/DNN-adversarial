(This is a topic in [README.md](../README.md).)

# Evaluating Reading-Comprehension Systems

Reading comprehension systems are capable of reading certain text and answer some question based on the information in the text. Robin Jia and Percy Liang propose two kinds of variation in generation of cases: `AddAny` which appends several random words to the *text*, and `AddSent` which appends a meaningful sentence (not contradicting original information) to the text. Both methods are semantics-preserving, such that the answer to the question should keep the same after text alternation.

## Reproduction

Luckily, this paper is shipped with complete solution that reproduces the result in [CodaLab](https://worksheets.codalab.org/worksheets/0xc86d3ebe69a3427d91f9aaa63f7d1e7d/).