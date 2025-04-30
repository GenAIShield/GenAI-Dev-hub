## Prompting Techniques: 
Link: 
[Guide Link](https://www.promptingguide.ai/techniques/zeroshot) , 
[Short notes linkedin link](https://www.linkedin.com/pulse/prompt-engineering-techniques-deepak-devassykutty-l9kfc?utm_source=share&utm_medium=member_ios&utm_campaign=share_via) ,
[linkedin link](https://www.linkedin.com/pulse/ai-prompt-engineering-react-framework-rany-elhousieny-phd%E1%B4%AC%E1%B4%AE%E1%B4%B0-ofhlc/)
### Zero-shot Prompting

  Zero-shot prompting means that the prompt used to interact with the model won't contain examples or demonstrations. The zero-shot prompt directly instructs the model to perform a task without any additional examples to steer it.
  example== Prompt:  Classify the text into neutral, negative or positive. 
                      Text: I think the vacation is okay.                          Output : Neutral
                      Sentiment:

### Few-shot Prompting

  - Few-shot prompting can be used as a technique to enable in-context learning where we provide demonstrations in the prompt to steer       the model to better performance. 
  - The demonstrations serve as conditioning for subsequent examples where we would like the model to generate a response.

    example == Prompt : A "whatpu" is a small, furry animal native to Tanzania. An example of a sentence that uses the word whatpu is:
                        We were traveling in Africa and we saw these very cute whatpus.
 
                    To do a "farduddle" means to jump up and down really fast. An example of a sentence that uses the word farduddle is:

               Output : When we won the game, we all started to farduddle in celebration.


### Chain-of-thought(CoT) Prompting

  - It is a technique used to enhance the reasoning capabilities of language models by encouraging them to "think step-by-step" through a problem or task. Rather than asking the model for a direct answer.
  - This method is particularly effective for tasks that involve logical reasoning, multi-step problems (like math, puzzles, or decision-making), or any scenario where intermediate steps are crucial to getting the correct answer.
  - One recent idea that came out more recently is the idea of zero-shot CoT (Kojima et al. 2022) that essentially involves adding "Let's think step by step" to the original prompt.
  - In few-shot CoT, you provide example and reasoning of that particular example.

### Meta Prompting

  - Meta Prompting is an advanced prompting technique that focuses on the structural and syntactical aspects of tasks and problems           rather than their specific content details.
  - The advantages of Meta Prompting over few-shot promoting include:
      1. Token efficiency: Reduces the number of tokens required by focusing on structure rather than detailed content.
      2. Fair comparison: Provides a more fair approach for comparing different problem-solving models by minimizing the influence of             specific examples.
      3. Zero-shot efficacy: Can be viewed as a form of zero-shot prompting, where the influence of specific examples is minimized.
   
  - It's important to note that meta prompting also assumes that the LLM has innate knowledge about the specific task or problem being       addressed.
  - As LLMs can generalize to a unseen tasks, it is possible that they can be leveraged with meta prompting but performance might             deteriorate with more unique and novel tasks as is the case with zero-shot prompting.

### Generate Knowledge Prompting

  - LLMs continue to be improved and one popular technique includes the ability to incorporate knowledge or information to help the          model make more accurate predictions.

  - Using a similar idea, can the model also be used to generate knowledge before making a prediction? That's what is attempted in the       paper by Liu et al. 2022 -- generate knowledge to be used as part of the prompt.

### Prompt Chaining

  - To improve the reliability and performance of LLMs, one of the important prompt engineering techniques is to break tasks into its        subtasks. Once those subtasks have been identified, the LLM is prompted with a subtask and then its response is used as input to         another prompt. This is what's referred to as prompt chaining, where a task is split into subtasks with the idea to create a chain       of prompt operations.

  - Prompt chaining is useful to accomplish complex tasks which an LLM might struggle to address if prompted with a very detailed            prompt. In prompt chaining, chain prompts perform transformations or additional processes on the generated responses before reaching     a final desired state.

  - Besides achieving better performance, prompt chaining helps to boost the transparency of your LLM application, increases                 controllability, and reliability. This means that you can debug problems with model responses much more easily and analyze and           improve performance in the different stages that need improvement.

### Tree-of-Thoughts(ToT)

 - ToT maintains a tree of thoughts, where thoughts represent coherent language sequences that serve as intermediate steps toward 
   solving a problem.

 - This approach enables an LM to self-evaluate the progress through intermediate thoughts made towards solving a problem through a 
    deliberate reasoning process.

 - The LM's ability to generate and evaluate thoughts is then combined with search algorithms (e.g., breadth-first search and depth- 
   first search) to enable systematic exploration of thoughts with lookahead and backtracking.

 - for example please visit : https://github.com/dave1010/tree-of-thought-prompting/blob/main/README.md

### Retrieval Augmented Generation(RAG)

 - Meta AI researchers introduced a method called Retrieval Augmented Generation (RAG) to address such knowledge-intensive tasks.
 - RAG combines an information retrieval component with a text generator model.
 - RAG can be fine-tuned and its internal knowledge can be modified in an efficient manner and without needing retraining of the entire 
   model.

### Automatic Reasoning and Tool-use (ART)

  - Combining CoT prompting and tools in an interleaved manner has shown to be a strong and robust approach to address many tasks with       LLMs. These approaches typically require hand-crafting task-specific demonstrations and carefully scripted interleaving of model         generations with tool use.
  -  Paranjape et al., (2023) propose a new framework that uses a frozen LLM to automatically generate intermediate reasoning steps as a      program.
  ART works as follows:
  - given a new task, it select demonstrations of multi-step reasoning and tool use from a task library
  - at test time, it pauses generation whenever external tools are called, and integrate their output before resuming generation.

  - for more information visit : https://arxiv.org/pdf/2303.09014

### Automatic Prompt Engineer(APE)

  - Zhou et al., (2022) propose automatic prompt engineer (APE) a framework for automatic instruction generation and selection. The          instruction generation problem is framed as natural language synthesis addressed as a black-box optimization problem using LLMs to       generate and search over candidate solutions.
  - The first step involves a large language model (as an inference model) that is given output demonstrations to generate instruction       candidates for a task. These candidate solutions will guide the search procedure. The instructions are executed using a target           model, and then the most appropriate instruction is selected based on computed evaluation scores.

### ReAct

  - Yao et al., 2022 introduced a framework named ReAct where LLMs are used to generate both reasoning traces and task-specific actions      in an interleaved manner.
  - Generating reasoning traces allow the model to induce, track, and update action plans, and even handle exceptions. The action step       allows to interface with and gather information from external sources such as knowledge bases or environments.
  - The ReAct framework can allow LLMs to interact with external tools to retrieve additional information that leads to more reliable        and factual responses.
