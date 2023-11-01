requires .net 7
had to add text embedding
the signalr is used for broadcast to multiple clients
it also is used to stream back to the client in the typescript see conversationSlice.ts
it doesn't pass through the content as it gets the tokens from openai, but rather concats them and sends the whole message, which gets rendered on the client

it has a citation source 
it calls into the semantic kernals GenerateMessageStreamAsync - this is an extension method on top of GetStreamingChatMessageAsync
not sure the difference between GenerateMessageStreamAsync and GetStreamingChatMessageAsync

GetUserIntentAsync -- does a call to openai to get user intent using custom made function that extracts the chat history and sends it to open ai

the safeInvokeAsync is curious

HandleBotResponseAsync is the meat

Interesting that they don't use the pipeline feature of the semantic kernel to run a bunch of sk functions. 

also, they don't use a sequential planner

has notion of content safety, but for images not text like us -- doesn't use it

they use the prompt template engine from semantic kernel
