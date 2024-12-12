## OpenAI Chat Completion API

### Explaining OpenAI Chat completion Parameters 

 While sending request to OpenAI chat completion API for text generation purpose, we need to pass several parameters to get the desired output. Here are the parameters that
 we need to pass:
 #### Model (model)
 This parameter specifies the GPT model to use for generating text. Most commonly used GPT models of OpenAI are `gpt-4o` and `gpt-4o-mini`.
 #### Messages (messages)
 The messages parameter is most important parameter for the OpenAI Chat Completion API. It's structured as an array of message objects, and each message object has two required fields: role and content. For rolw filed , it can be either _**user**_ or _**assistant**_. For `content` field, it can be any text of the message. Whether it's a system instruction, a user query, or a previous assistant response, the content goes here. Example given below :  

    message : [{"role": "system", "content": "You are a helpful and harmless AI assistant."},
    {"role": "user", "content": "What is the capital of France?"},
    {"role": "assistant", "content": "The capital of France is Paris."},
    {"role": "user", "content": "And what is its      population?"}
    ]


 #### Max Completion Tokens (max_completion_tokens)
 This parameter specifies the  upper bound for the number of tokens that can be generated for a completion,
 
 #### n
 How many chat completion choices to generate for each input message. Note that you will be charged based on the number of generated tokens across all of the choices. Keep n as 1 to minimize costs.

 #### Stream 
 If  stream parameter set to true, partial message deltas will be sent, like in ChatGPT. Tokens will be sent as data-only server-sent events as they become available, with the stream terminated by a data: [DONE] message.
 #### Temperature
What sampling temperature to use, between 0 and 2. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic.
 #### top_p

An alternative to sampling with temperature, called nucleus sampling, where the model considers the results of the tokens with top_p probability mass. So 0.1 means only the tokens comprising the top 10% probability mass are considered.

 #### tools

A list of tools the model may call. Currently, only functions are supported as a tool. Use this to provide a list of functions the model may generate JSON inputs for. A max of 128 functions are supported.