
# Lab 5 - Improving Transcribe using Custom Language Model
Custom language models are designed to improve transcription accuracy for domain-specific speech. This includes any content outside of what you would hear in normal, everyday conversations. For example, if you're transcribing the proceedings from a scientific conference, a standard transcription is unlikely to recognize many of the scientific terms used by presenters. In this case, you can train a custom language model to recognize the specialized terms used in your discipline.

**NOTE**:
Unlike custom vocabularies, which increase recognition of a word by providing hints (such as pronunciations), custom language models learn the context associated with a given word. This includes how and when a word is used, and the relationship a word has to other words. For example, if you train your model using climate science research papers, your model may learn that 'ice floe' is a more likely word pair than 'ice flow'.

**In this lab, you will learn**

✅ You will understand the context of Custom Language Models

✅ How to calculate Word Error Rate(WER) for the ground truth

✅ How to compare WER of base model Transcribe transcription against ground truth

✅ How to prepare your data for CLM training

✅ How to train your CLM model

✅ How to assess the accuracy improvements based on WER of CLM model against the base model
