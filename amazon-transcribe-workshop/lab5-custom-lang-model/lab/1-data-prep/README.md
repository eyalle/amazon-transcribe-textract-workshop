---
title : "Data preparation"
weight : 55
---

Before we begin, it’s important to distinguish between _training data_ and _tuning data_.

### Training data
 Custom Language Models typically includes text data that is specific to your domain. Some examples of training data could include relevant text content from your website, training manuals, sales and marketing collateral, or other text sources.

### Tuning data
Meanwhile, human-annotated audio transcripts of actual phone calls or media content that are directly relevant to your use case can be used as tuning data.

:warning: [For more information about the difference between training and tuning data, see [Improving Domain-Specific Transcription Accuracy with Custom Language Models](https://docs.aws.amazon.com/transcribe/latest/dg/custom-language-models.html).]

## Use case - Video Gaming
>Like many domains, video gaming has its own set of technical jargon, syntax, and speech dynamics that may make the use of a general speech recognition engine suboptimal. To build a custom model, we first need data that’s representative of the domain. For this use case, we want free form text from the video gaming industry. We use a variety of publicly available information from a variety of sources about video gaming. 

Let's get started:

1. Download training and tuning set from here [download](https://aws-ml-blog.s3.amazonaws.com/artifacts/Building-Custom-Language-Models/training_tuning_data.tar.gz) to follow along.

:warning: [NOTE: Keep in mind that the nature, quality, and quantity of your training data has a dramatic impact on the resultant custom model you build. All else equal, it’s better to have more data than less.]

As a general guideline, your training and tuning datasets should meet the following parameters:
-   Is in plain text (it’s not a file such as a Microsoft Word document, CSV file, or PDF).
-   Has a single sentence per line.
-   Is encoded in UTF-8.
-   Doesn’t contain any formatting characters, such as HTML tags.
-   Is less than 2 GB in size if you intend to use the file as training data. You can provide a maximum of 2 GB of training data.
-   Is less than 200 MB in size if you intend to use the file as tuning data. You can provide a maximum of 200 MB of optional tuning data.

The following test is a partial snippet of our example training set:

> The PS5 will feature a custom eight-core AMD Zen 2 CPU clocked at 3.5GHz (variable frequency) and a custom GPU based on AMD’s RDNA 2 architecture hardware that promises 10.28 teraflops and 36 compute units clocked at 2.23GHz (also variable frequency).
> 
> It’ll also have 16GB of GDDR6 RAM and a custom 825GB SSD that Sony has previously promised will offer super-fast loading times in gameplay, via Eurogamer.
> 
> One of the biggest technical updates in the PS5 was already announced last year: a switch to SSD storage for the console’s main hard drive, which Sony says will result in dramatically faster load times.
> 
> A previous demo showed Spider-Man loading levels in less than a second on the PS5, compared to the roughly eight seconds it took on a PS4.PlayStation hardware lead Mark Cerny dove into some of the details about those SSD goals at the announcement.
> 
> Where it took a PS4 around 20 seconds to load a single gigabyte of data, the goal with the PS5’s SSD was to enable loading five gigabytes of data in a single second.
