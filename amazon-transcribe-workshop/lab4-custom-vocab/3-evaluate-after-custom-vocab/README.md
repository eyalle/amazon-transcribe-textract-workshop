
# Evaluate after custom vocabulary
weight: 44


Now, it's time to evaluate the accuracy after using custom vocabulary.

1. Let's start another new transcription job for the same audio file, but this time, we’ll invoke the custom vocabulary text file to see the accuracy results. The process is the same as we had been through before, except this time we will actually designate a custom vocabulary “paul-sample-vocab”. And of course, I’ll name the transcription job something different from the first one, like “customer-call-with-vocabulary”:

    ![](../static/images/lab3-custom-vocab/custom-vocab-2.png)

    Select defaults on the rest of the selections and click 'Next'.

2. On the next screen, toggle 'Custom Vocabulary' to on and select the custom vocabulary created in the previous section.

    ![](../static/images/lab3-custom-vocab/custom-vocab-7.png)


3. Once the job is complete, take a look at the new transcription results now!

    ![](../static/custom-vocab-10.gif)

    Here’s the transcription output:

    > “Hi. My name is Paul, and I’m calling in about my order of two separate **LEGO** toys. The first one is the Harry Potter Hogwarts Castle. That has a cool Grindelwald **mini-fig**. The second set is a model of the **Lotus Elise** car. I placed the orders on the same day. Can you tell me when they will be arriving, please?”

We’ve not only correctly transcribed custom formal nouns such as “Grindelwald” but also custom terms like “mini-fig” which are specific to LEGO toys. And look at that, we also were able to properly capitalize “LEGO” as it is spelled as a brand, along with proper casing for “Lotus Elise” as well.


Custom vocabulary should be used in a targeted manner, meaning that the more specific a list of terms is when applied to specific audio recordings, the better the transcription result. We don’t recommend flooding a single vocabulary file with more than 300 words. The feature is available in all regions where Transcribe is available today.

Congrats, you have now completed Custom Vocabulary lab, time to move on to building Custom Language Models!
