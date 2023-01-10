---
title : "Training your custom language model"
weight : 56
---


In the following steps, you will train a CLM using base training data and a tuning split. Using a tuning split is entirely optional. If you prefer not to train a CLM using a tuning split, you can skip step 5.

1.  [Upload](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/upload-objects.html) your training data (and/or tuning data) to their respective [Amazon Simple Storage Service](http://aws.amazon.com/s3) (Amazon S3) buckets.

2.  On the Amazon Transcribe console, for **Name**, enter a name for your custom model so you can reference it for later use.

3.  For **Base model**, choose a model type that matches your use case, based on [audio sample rate](https://en.wikipedia.org/wiki/Sampling_(signal_processing)).

4.  For **Training data**, enter the appropriate S3 bucket where you previously uploaded your training data.

5.  For **Tuning data**, enter the appropriate S3 bucket where you uploaded your tuning data. (This step is optional)

6.  For **Access permissions**, designate the appropriate [access permissions](https://docs.aws.amazon.com/transcribe/latest/dg/training-data-permissions.html).

7.  Choose **Train model**.

![](../static/1-Train-the-model.jpg)

:warning: [Amazon Transcribe service does the heavy lifting of automatically training a custom model for you.]

8. To track the progress of the model training, go to the **Custom language models** page on the Amazon Transcribe console. The status indicates if the training is in progress, complete, or failed.

![](../static/2-Screenshot-4.jpg)

This can take anywhere from 2 to 3 hours.
