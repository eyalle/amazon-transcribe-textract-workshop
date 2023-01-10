---
title : "Evaluating the results"
weight : 59
---
In this section, we will go through a series of steps to measure the WER using asr-eval that you setup in the previous step.

1. First create a folder called 'transcribe-workshop-clm-eval' along with empty .txt files as shown below. In the subsequent steps, we will copy the text into the corresponding files to do the WER tests.
    
    ![](../static/images/lab4-clm/wer-testing-folder.png)

2. As addressed earlier, we will start with ground truth as the base, then compare it against base model and CLM models to show the accuracy improvements. Copy the following 'ground truth' to **transcribe-workshop-clm-ground-truth.txt**

    >The 2020 holiday season is right around the corner. And with the way that the year’s been going, we can all hope for a little excitement around the next-gen video game consoles coming out soon. So, what’s the difference in hardware specs between the upcoming Playstation 5 and Xbox Series X? Well, let’s take a look under the hoods of each next-gen gaming console. The PS5 features an AMD Zen 2 CPU with up to 3.5 GHz frequency. It sports an AMD Radeon GPU that touts 10.3 teraflops, running up to 2.23 GHz. Memory and storage respectively dial in at 16 GB and 825 GB. The PS5 supports both PS The PS5 supports both 4K and 8K resolution screens. The Xbox Series X also features an AMD Zen 2 CPU, but clocks in at 3.8 GHz instead. The console boasts a similar AMD custom GPU with 12 teraflops and 1.825 GHz.

    >Memory is the same as that of the PS5’s, coming in at 16 GB. But the default storage is where the system has an edge, bringing out a massive 1 TB hard drive. Like the PS5, the Series X also supports 4K and 8K resolution screens as well. Those of course, are just the numbers. Therefore, it remains to be seen exactly how the performance plays out in practice. It’s worth noting that both systems have incorporated ray-tracing technology, something that’s used to make light and shadows look better in-game. Both systems also offer 3D audio output for immersive experiences.


3. Next, run a batch transcription against this audio file using the base model as described in Lab1 batch processing. First, download the [audio sample](https://aws-ml-blog.s3.amazonaws.com/artifacts/Building-Custom-Language-Models/clm-blog-16k-audio.m4a) and store it into S3 bucket. Next, select 'Transcription jobs' from Transcribe console. Then, create the job by pointing to the audio file in the S3 bucket.

    ![](../static/images/lab4-clm/clm-create-general-model-job.png)

4. After the transcription job is finished, copy the plain text from the job and save it into **transcribe-workshop-clm-base-model.txt**.
   
   Go to the transcription jobs, find the general model job you ran in the previous step and select that. In the transcription preview section, download the json.
   ![](../static/images/lab4-clm/clm-download-json.png)
   
   Copy the text form json file you just downloaded as shown below to **transcribe-workshop-clm-base-model.txt**.
   ![](../static/images/lab4-clm/clm-copy-transcription.png)
    
5. Now, we are ready to calculate the WER against the base model. Open your command line interface, change your directory to  'transcribe-workshop-clm-eval' which is created in step 1. Then, execute the following commands to capture the WER:

    :::code
        % asr-eval --original transcribe-workshop-clm-ground-truth.txt --generated transcribe-workshop-clm-base-model.txt  
        Word Error Rate (WER): 25.19 %

        Word Information Loss (WIL): 36.41 %
    :::

    Pay attention to WER percentage.
    
6. Next, we will capture the transcription from the CLM job with just training and no tuning data - that you ran in the last section.

     
   Follow similar steps as you did in the last step - go to the transcription jobs, find the CLM transcription job with no tuning and copy the transcription into **transcribe-workshop-clm-training-no-tuning.txt** . 
   
   Then, execute the following command to capture the WER.
   
   :::code
        % asr-eval --original transcribe-workshop-clm-ground-truth.txt --generated transcribe-workshop-clm-training-no-tuning.txt
        Word Error Rate (WER): 20.30 %

        Word Information Loss (WIL): 31.04 %
   :::

   
 7. Next, follow similar steps to calculate WER against the CLM model with both training and tuning data.  

    :::code
        % asr-eval --original transcribe-workshop-clm-ground-truth.txt --generated transcribe-workshop-clm-training-tuning.txt
        Word Error Rate (WER): 18.70 %

        Word Information Loss (WIL): 30.64 %
    :::

    If you observe the WER this time, it is much lesser compared to CLM model with just training. As you can see, customers get great accuracy advancements using CLM.
---

#### Analyze the results

We can now analyze the results. The below table shows the WER decreasing.

| Transcription Type | WER (%) | Accuracy (100-WER) | 
| --- | ----------- | ----|
| Amazon Transcribe generic model | 25.19% | 74.81% | 
| Amazon Transcribe CLM with no tuning split | 20.30 % | 79.7% |
| Amazon Transcribe CLM with tuning split | 18.70% | 81.3% |

---

To give a qualitative visual comparison, we’ve taken a snippet of the transcript from each CLM’s output and put it against the original human annotated reference transcript to share a qualitative comparison of the different terms that were recognized by each model. 

![](../static/images/lab4-clm/clm-wer-comparisons.png)


✅ Custom Language Model using training data performed ~5% better. 

✅ And the CLM built using training data and a tuning split performed approximately ~13% better.


:warning: [For more information about the general guidelines, see [Improving Domain-Specific Transcription Accuracy with Custom Language Models](https://docs.aws.amazon.com/transcribe/latest/dg/custom-language-models.html).]

Congrats, you have now completed the Custom langauge model lab!
