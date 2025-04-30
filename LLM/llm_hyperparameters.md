### Important Parameters involved in a LLM

1) Temperature :
    - Controls the randomness of the model's output
    - Lower values (closer to 0) make the output more deterministic and focused on the most probable completions.
    - Higher values (closer to 1 or above) allow for more randomness and creative responses.

2) Maximum length :
     - Defines the maximum number of tokens (words or parts of words) that the model will generate. In the image, it's set to 256, meaning the model can produce up to 256 tokens in its response.
  
3) Stop sequences :
   - A specific string of characters that stops the model's output when encountered.
  
4) Top P :
   - It restricts the model to consider only the top cumulative probability tokens, ensuring a more focused output.
   - For example, if top-p is set to 0.9, the LLM will only generate words with a probability of at least 0.9. This can result in more        diverse text, but less fluent.
     
5) Top K :
   - The model always picks from the top K tokens ranked by their individual probabilities. If K = 50, the model will always consider the top 50 highest probability tokens, no matter how likely they are.
  
7) Frequency penalty:
    - This parameter penalizes the model for using words too frequently.
    - A higher value encourages more variety by discouraging word repetition.


links: https://peterchng.com/blog/2023/05/02/token-selection-strategies-top-k-top-p-and-temperature/#:~:text=Summary,certain%20probability%20mass%20(p)
