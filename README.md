# AI-Learning
Learning AI One-Day At a Time


# Topics 

1. Long-text Summarization technqiues.
   (Chunking algorithms that keep the structure of contextual information and reduce data variance at runtime is the key here)
   There is a limited token size which GPT can take 4096 tokens at a time. You cannot fit all the large text into it in a single shot. But      this isn’t the limit on just the size of the next message you send… The combined length of everything needs to be short enough. That is,     all of the following together must be under this 4,096 token limit: The whole chat history, Your next message, ChatGPT’s next reply

   This is because ChatGPT doesn’t actually have a memory of your conversation–it just re-reads the whole conversation every time it replies!
   Once you go past the 4,096 token limit, OpenAI starts to drop the oldest parts of your conversation (behind the scenes) in order to make     room for new dialogue. Recency bias due to token limit. Why 4096 ( 2^12), as it requires a high GPU to process all the conversations.

   Solutions:
   1. Stuffing method
   2. MapReduce method
   3. MapReduce with Overlapping Chunks method
   4. MapReduce with Rolling Summary method
      
   https://github.com/GoogleCloudPlatform/generative-ai/blob/main/language/use-cases/document-summarization/summarization_large_documents.ipynb

2. Document QA
   Same steps as above, but we pass the chunks to embedding model to create vector space embedding and store them in DB(** Need to read more)
   Then againg for question, we will create embedding and find the nearest Top 2-5 vectors embedding from vector space. And give it as          answer to the questions
   https://github.com/GoogleCloudPlatform/generative-ai/blob/main/language/use-cases/document-qa/question_answering_documentai_vector_store_palm.ipynb

3. Grounding
   https://www.k2view.com/blog/llm-grounding/#Extending-RAG-with-GenAI-Data-Fusion
   
   What are Grounding LLMs? Grounding LLMs refer to the approach of incorporating specific data or context into language models to provide      more accurate and domain-specific responses. While traditional language models like ChatGPT are trained on vast amounts of general text      data, they may lack the ability to generate precise answers based on specific knowledge sources. Grounding LLMs aim to overcome this         limitation by allowing models to generate responses that are grounded in real-world information relevant to a particular domain or           dataset.
   Benefits:
   1. Less hallucination 
   2. Better context and domain specific knowledge beating general model standards. 
   3. Enhances the trustworthiness, accuracy, and applicability of the generated content( Most important in org. level )
   4. Reduced Bias

   Techniques: RAG based applications

   What's the difference between fine-tuning and Grounding ?
   Grounding focuses on making a model's responses relevant to the current context or environment without changing the model’s underlying parameters. General bot with specific knowledge of HR, finance, tech
   Fine-tuning involves retraining a pre-trained model on new data to specialize it for a specific task, which alters the model's parameters to improve performance.  Finance Bot
   https://www.k2view.com/blog/retrieval-augmented-generation-vs-fine-tuning/#Data-Products-for-RAG-and-Fine-Tuning

   Usage: Chatbot to chat with HR, Finance. 
https://medium.com/@prajeeshprathap/understanding-grounding-llms-and-retrieval-augmented-generation-3a72c74a1d99


Resources:
https://github.com/GoogleCloudPlatform/generative-ai/blob/main/language/prompts/examples/text_summarization.ipynb
https://github.com/anthropics/courses/tree/master/prompt_engineering_interactive_tutorial
