# confidence_scoring-LLM
An attempt to score the uncertainty in "Next Line Prediction" from Language Models of Code

## Overview
Next Line Code Prediction is a highly uncertain task. The model prediction of the next line depends on the patterns it has observed in the code context. Pattern could be anything ranging from a similar code block to a known variable like “logits” instead of using variable “result”. A model better understands what to do in the next line if it has come across any variable which it is familiar with or is associated with a particular operation to be performed in the next line.

Not every context is enough to predict the next line. Log probabilities of the first few tokens are an indicator if the model is confident about its prediction given the context. As observed, the model may hallucinate in predicting the first few tokens if it is not able to lead the next lines of the context code.

The code weighs the probability of the first few tokens (<5) with sequence of weights like (0.9, 0.05, 0.025..).

