# LLMZoomCamp Kaggle Competition Winning Solution

## Introduction
As a newcomer to the world of Large Language Models (LLMs), participating in the LLMZoomCamp competition was an incredible learning experience. The journey from having no prior experience with LLMs to developing a winning solution was both challenging and rewarding. One might wonder where in the field you would need to solve math problems with LLMs, and if it's even useful. My answer is yes; the techniques I learned, such as structured outputs, chain of thought reasoning, multithreading, and error handling with retry mechanisms, can elevate most LLM-based applications to the next level.

## High-Level Solution Overview
My solution leveraged the power of Claude-3.5 Sonnet, combining zero-shot chain of thought reasoning with Python code generation and execution. The intuition was that while LLMs might not always excel at math computations, they are quite proficient at generating code. Thus, the additional step of validating the answer by executing the code proved to improve the accuracy of the final answers.

The process flow was as follows:

1. Creating two answers based on zero-shot chain of thought reasoning:
    - 1st answer based on reasoning without code
    - 2nd answer based on reasoning by executing generated Python code derived from the reasoning flow
2. Comparison of results:
   - If the reasoning and code execution answers matched, we considered it correct.
   - In case of discrepancies, an additional LLM reasoning step was used to determine the correct answer.

To ensure robustness and reliability, I implemented:
- [Instructor](https://github.com/jxnl/instructor) validation for guaranteeing executable Python code.
- A timeout mechanism to prevent infinite loops in code execution.
- Error message feedback to the LLM for retries and improvements in case of code execution errors.

## Sharing Knowledge Through Medium Articles
Throughout the competition, I documented and shared key insights and techniques through a series of Medium articles. These articles solidified my understanding and serve as a resource for others interested in LLM applications, including short, practical examples. Here are the key articles:

1. [Structured Outputs and Effective Prompting](https://medium.com/@arturgrygorian3/solving-math-problems-with-llms-fed77f4cf4ec) - Using the Instructor library to create structured outputs from LLMs, ensuring consistent and parseable responses for math problems.

2. [Deep Dive into Instructor's Inner Workings](https://medium.com/@arturgrygorian3/solving-math-problems-with-llms-921e287f5796) - Exploring how Instructor generates schemas for function calling. 

3. [Executing Python Code Safely](https://medium.com/@arturgrygorian3/solving-math-problems-with-llms-e28cebfd2b82) - Generating Python code from LLM responses and executing it safely.

4. [Multithreading for Robust Response Generation](https://medium.com/@arturgrygorian3/solving-math-problems-with-llms-fed77f4cf4ec) - Using multithreading to solve multiple math problems concurrently, improving overall system efficiency.

5. [Mastering Error Handling and Retries](https://medium.com/@arturgrygorian3/solving-math-problems-with-llms-ec92c2a13797) - Implementing robust error handling and retry mechanisms.

These articles contribute back to the community by sharing practical insights gained during the competition.
