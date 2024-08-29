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
