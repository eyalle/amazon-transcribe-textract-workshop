
# CLM - Establishing the context

To evaluate Custom Language Models (CLM) to enhance transcription accuracy, here are the steps:
 
###### First we establish a baseline
 To do that, we recorded an [audio sample](https://aws-ml-blog.s3.amazonaws.com/artifacts/Building-Custom-Language-Models/clm-blog-16k-audio.m4a) that contains speech content and lingo commonly found in video game chats. We also have a human-generated transcription to benchmark the **ground truth**. 
 
 This ground truth transcript serves as the reference transcript we use to compare the general transcription output of Amazon Transcribe and the output of CLM. The following is a partial snippet of this reference transcript.

### Ground Truth

Pay attention to the words that are very specific to the domain in bold.

> The 2020 holiday season is right around the corner. And with the way that the year’s been going, we can all hope for a little excitement around the next-gen video game consoles coming out soon. So, what’s the difference in **hardware specs** between the upcoming Playstation 5 and Xbox Series X? Well, let’s take a look under the hoods of each next-gen gaming **console**. The PS5 features **an AMD Zen 2 CPU** with up to 3.5 GHz frequency. It sports **an AMD Radeon** GPU that **touts** 10.3 teraflops, running up to 2.23 GHz. Memory and storage respectively **dial in** at 16 GB and 825 GB. The PS5 supports both PS The PS5 supports both 4K and **8K resolution** screens. Meanwhile, the Xbox Series X also features an **AMD Zen 2 CPU**, but clocks in at **3.8 GHz** instead. **The console boasts a similar AMD custom** GPU with 12 teraflops and 1.825 GHz. Memory is the same as that of the PS5’s, **coming in at** 16 GB. But the default storage is where the system has an edge, bringing out a massive 1 TB hard drive. Like the PS5, the **Series X** also supports 4K and 8K resolution screens as well. Those of course, are just the numbers. Therefore, it remains to be seen exactly how the performance plays out in practice. It’s worth noting that both systems have incorporated ray-tracing technology, something that’s used to make light and shadows look better in-game. Both systems also offer 3D audio output for immersive experiences.

**Next, we will run through Transcribe to generate the transcript to compare against the ground truth.**

We will use **Word Error Rate (WER)** [Word Error Rate](https://en.wikipedia.org/wiki/Word_error_rate)as a measure of accuracy. Lower the WER, higher the accuracy. You will go through measuring WER in this lab.

:warning: [Note that this WER is not a representation of the Amazon Transcribe service performance. It is just one instance for a very specific and limited test example.]



