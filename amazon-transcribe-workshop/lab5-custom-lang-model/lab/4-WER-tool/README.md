---
title : "Install Word Error Rate Tool"
weight : 58
---

In this section, you are going to learn how to use a Word Error Rate tool to measure the accuracy of the transcription with reference to the ground truth.

The word error rate is based on how much the word string returned by the recognizer (the hypothesized word string) differs from a reference transcription. The first step in computing word error is to compute the minimum edit distance in words between the hypothesized and correct strings, giving us the minimum num- ber of word substitutions, word insertions, and word deletions necessary to map between the correct and hypothesized strings. The word error rate (WER) is then defined as follows (note that because the equation includes insertions, the error rate can be greater than 100%):

![](../static/images/lab4-clm/wer-calculation.png)

Within the context of this lab, we are going to use asr-eval, an open-source tool from https://github.com/symblai/speech-recognition-evaluation.

1.  Head over to https://github.com/symblai/speech-recognition-evaluation, follow the instructions on the github website to setup the tool on your local machine. 

2.  Make sure you are able to execute asr-eval on your command line and the response is back as shown below:
    ::code[ % asr-eval ]

    Response should be as following: 

    ![](../static/images/lab4-clm/asr-eval-response.png)

3. Since we did not specify the original file and reference file, you will see the errors, just ignore them. We are making sure the tool is working at this point. Later, in the next section, we are going to use this tool to evaluate the results pre and post CLM.

