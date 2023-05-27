# About
Study Notes for the ChatGPT deeplearning.ai which is located [here](https://learn.deeplearning.ai/chatgpt-prompt-eng).
I used ChatGPT to improve the wording.


## Class 1: Guidelines
This section is about some of the tips and tricks when writing prompts for ChatGPT.

There are 2 principles here:
1. Write clear and specific instructions. (how to write prompts)
2. Give the model time to think. (Use technics like chain-of-thought)

### Principle 1, Tactic 1: Use delimiters to separate out distinct parts of the input
Delimiters can be anything like: ```, """, < >, or html tags

### Principle 1, Tactic 2: Specify for a structured output
Examples include JSON or HTML. 
This allows ChatGPT to output an answer that can be parsed later.

### Principle 1, Tactic 3: Ask the model to check if the input is valid

Often in times with ChatGPT apps, we have the task description and context.
You can add something like "if the text does not fit the description, output None"
so that ChatGPT can auto validate the input.

### Principle 1, Tactic 4: Few-Shot Prompting

This part is pretty standard. Provide some examples and let ChatGPT continue to generate. For example:

```
Write in a consistent style.

Q: Teach me about patience.
A: <A poem about patience>

Q: Teach me about resilience.
A: <ChatGPT will answer this>
```

### Principle 2, Tactic 1: Specify the steps required 
If the job you want ChatGPT to do is complicated, then don't just let it output an answer.
Tell it to do the task in multiple steps with outputs to generate a better answer.

(I skipped the example from class since I noticed ChatGPT is actually able to do that task right away)

### Principle 2, Tactic 2: Instruct the model to workout its solution then make conclusion
This is more of a more specific case of tactic 1. The situation is that we want
to build a bot that checks the student's solution for a math problem. Instead of just outputting the yes/no answer.
It is better to instruct ChatGPT to write out its own solution first, and then compare it with the student's answer.

### Hallucinations  
A common way to reduce hallucination is to find relevant information first (for example, from the internet). 
Provide the context and ask ChatGPT to answer the question based on the relevant information.


## Class 2: Iterative

This class goes over the iterative process to develop a prompt that suites your use case. 
The example that was given is to write a production description for furnitures. In general, follow the steps to develop prompts:

1. Gather idea to improve/create the prompt
2. Write out the prompt
3. Experiment it with examples
4. Analyze the output and see if there are areas to improve
5. Rinse and repeat

## Class 3: Summarizing

### Constraining the output size
There are few ways to make the output more succinct. Such as
1. Limiting the number of characters (does not work well because ChatGPT understands by tokens)
2. Limiting by the number of words (Does a okish job)
3. Limiting by the number of sentences (works well)

When writing summaries, you can also tell ChatGPT who the intended audience is so it can 
focus on parts that are more relevant to the reader.

Instead of saying `summarize`, try to use `extract` and it would work better to only get
the information you are looking for without including unnecessary parts.

## Class 4: Inferring

One can use ChatGPT to extract a piece of text's sentiment. The most classical example being verifying either the sentiment is positive or negative. We can also as the LLM to output a list of emotions or verifying if the piece of text expresses certain emotion.

### Information Extraction

Another useful inference the prompt can do is to extract information such as item and brand from customer reviews. It is also possible to specify the output as JSON so it is in a parsable way. One can combine the sentiment analysis from above to outpuut multiple information at once.

### Topic Extraction
Additionally, LLM is good at inferring topics. Given a large piece of text, the LLM is able to extract a list of topics discussed by the text.

Alternatively, you can have a fixed set of topics, and ask the LLM whether or not the text inputs contain any of the topics. This is an example of zero-shot learning. A possible derived product from this feature is to build a news alert/subscription service.

## Class 5: Transforming
### Translation

Things can you do with multiple natural languages:
- Translate from one language to another (or even multiple at once)
- Check which language the text is in
- The translation task can also take account of the tone of the translation

One application based on translation is a universal translator. For each IT request in different languages, you can ask ChatGPT to identify the language and provide translation of that language to English.

### English tasks

Tone translation: convert between formal/informal text
Format Conversion: trasnlate from JSON to HTML (table), you can also output to Markdown, etc.
Proofreading: Fix spelling and grammar

The above technics can be combined together.

## Class 6: Expanding

You can use ChatGPT to automatically generate responses to reviews. In this example, we made prompt to automatically reply to customer reviews, taking in consideration of their sentiment.

Through the use of tempature, ChatGPT is able to generate more dynamic responses (by selecting less likely words). The responses generated that way will give more variety and creativity.

Lastly, you can add more details in the prompt to tell ChatGPT to focus on the details of the reviews and make replies based on those information in the text. This can make the response more relevant.

## Class 7: Chatbot

One application of ChatGPT is that you can build a custom Chatbot that fits your specific use case.

The example given was a pizza ordering bot which asks the users about the details of the order (such as pizza kind, size, extra toppings).

We can then take the conversation history and ask ChatGPT to generate a recipt.
