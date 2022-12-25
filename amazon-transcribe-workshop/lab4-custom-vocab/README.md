---
title: 'Lab 4 - Improving accuracy using Custom Vocab'
weight: 41
---

**In this lab, you learn**

✅  How to transcribe prior to using custom vocabulary

✅  Then, how to use custom vocabulary to improve the accuracy

✅  Lastly, how to evaluate the accuracy after using custom vocabulary

----

**NOTE**:
In this lab, we will focus on creating custom vocabulary using tables using the AWS Console.

Use custom vocabularies to improve transcription accuracy for one or more specific words. These are generally domain-specific terms, such as brand names and acronyms, proper nouns, and words that Amazon Transcribe isn't rendering correctly.

:::alert{header="Important" type="warning"}
You are responsible for the integrity of your own data when you use Amazon Transcribe. Do not enter confidential information, personal information (PII), or protected health information (PHI) into a custom vocabulary.
:::

> Custom vocabulary is a powerful feature that helps users transcribe terms that would otherwise not be part of our general ASR service. For instance, your use case may involve brand names or proper names that are not normally part of a language model’s regular lexicon, like in the case of “Hogwarts”. In this case, it would not only be helpful to be able to add the custom text, but also be able to inform our ASR service on the pronunciation to help our system better recognize unfamiliar terms. On a related note, perhaps you have a term, say, “Lotus” which is a brand name of a car. Naturally, we recognize “lotus” as a flower already. But for your use case, you’d like to have the word transcribed with proper capitalization in the context of recognizing it as a make or model of a vehicle. You can therefore use the recently added custom display forms to achieve this.



For other considerations and best practices for using custom vocabularies, please refer to this [documentation](https://docs.aws.amazon.com/transcribe/latest/dg/custom-vocabulary.html)
