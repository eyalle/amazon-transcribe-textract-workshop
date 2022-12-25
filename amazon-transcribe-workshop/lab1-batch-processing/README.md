
# Lab 1 - Batch processing

Prior to starting a batch transcription, you must first upload your media file to an Amazon S3 bucket. If you're unsure how to do this, refer to the Amazon S3 User Guide: [Upload an object to your bucket](https://docs.aws.amazon.com/AmazonS3/latest/userguide/uploading-an-object-bucket.html)

**If you don't have an audio file to test, you can download [sample audio](../static/audio/demo-call.mp3).**

1.  From the [AWS Management Console](https://console.aws.amazon.com/transcribe), select **Transcription jobs** in the left navigation pane. This takes you to a list of your transcription jobs.
    
    ![Amazon Transcribe console screenshot: the 'transcription jobs' page.
                        ](../static/console-batch-1.png)
    
    Select **Create job**.
    
2.  Complete the fields on the **Specify job details** page.
    
    ![Amazon Transcribe console screenshot: the 'specify job details' page.](../static/console-batch-job-details-1.png)
    
    The input location _must_ be an object within an Amazon S3 bucket. For output location, you can choose a secure Amazon S3 service-managed bucket or you can specify your own Amazon S3 bucket.
    
    If you choose a service-managed bucket, you can view a transcript preview in the AWS Management Console and you can download your transcript from the job details page (see below).
    
    If you choose your own Amazon S3 bucket, you cannot see a preview in the AWS Management Console and must go to the Amazon S3 bucket to download your transcript.
    
    ![Amazon Transcribe console screenshot: the input and output data panes for a batch transcription.](../static/console-batch-job-details-2.png)
    
    Select **Next**.
    
3.  Choose default settings in the **Configure job** page. If you want to learn more about [Custom vocabularies](https://docs.aws.amazon.com/transcribe/latest/dg/custom-vocabulary.html) or [Custom language models](https://docs.aws.amazon.com/transcribe/latest/dg/custom-language-models.html), you can try them out in lab 3 and lab 4.
    
    ![Amazon Transcribe console screenshot: the 'configure job' page.](../static/console-batch-configure-job.png)
    
    Select **Create job**.
    
4.  You're now on the **Transcription jobs** page. Here you can see the status of the transcription job. Once complete, click on the name of your transcription.
    
    ![Amazon Transcribe console screenshot: the transcription jobs summary page.](../static/console-batch-transcription-jobs.png)
    
5.  You're now viewing the **Job details** page for your transcription. Here you can view all of the options you specified when setting up your transcription job.

    ![Amazon Transcribe console screenshot: summary page for completed transcription.](../static/console-batch-complete.png)
    
    
6.  How you download your transcript depends on whether you chose a service-managed Amazon S3 bucket or your own Amazon S3 bucket.
    
    1.  If you chose a service-managed bucket, you can see a **Transcription preview** pane on your transcription job's information page, along with a **Download** button.
        
        ![Amazon Transcribe console screenshot: summary page for transcription in a service-managed bucket.](../static/console-batch-output-service-s3.png)
        
        Select **Download** and choose **Download transcript**.
        
    2.  If you chose your own Amazon S3 bucket, you don't see any text in the **Transcription preview** pane on your transcription job's information page. Instead, you see a blue information box with a link to the Amazon S3 bucket you chose.
        
        ![Amazon Transcribe console screenshot: summary page for transcription in a self-managed bucket.](../static/console-batch-output-own-s3.png)
        
        To access your transcript, go to the specified Amazon S3 bucket using either the link under **Output data location** in the **Job details** pane or the **S3 Bucket** link within the blue information box in the **Transcription preview** pane.

5. To download the .json output of the Transcribe API response, click on the 'Download' dropdown which is far right to the 'Transcription Preview' window.

    ![Amazon Transcribe console screenshot: download json.](../static/console-batch-download-json.png)
        
