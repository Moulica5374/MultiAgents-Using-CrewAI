 # Multi-Agent Customer Support System using CrewAI

 ## Overview
This project demonstrates an AI-powered multi-agent architecture for automated customer support using CrewAI. Each agent in the crew is designed with a unique persona — handling specific aspects like answering FAQs, resolving complaints, upselling products, and technical troubleshooting.

It simulates how modern customer service can be automated through intelligent collaboration between specialized agents.

## Use Case
“Automate the process of responding to customer queries, escalating technical issues, and offering personalized product recommendations — all via coordinated agents.”

## Tech Stack

| Component      | Tool/Library              |
| -------------- | ------------------------- |
| Framework      | `CrewAI`                  |
| Language Model | `OpenAI GPT-4` / `Gemini` |
| Orchestration  | `LangChain`               |
| Environment    | `Python`                  |
| Notebook       | `Jupyter / Colab`         |


## CrewAI Agent-Based Workflow Syntax
This section explains how the CrewAI framework models intelligent collaboration through Agents, Tasks, and Crews.

### Agent
Each Agent is a persona with a defined role, goal, and optional backstory. It is powered by an LLM and handles specific expertise.

| Field       | Description                                                                |
| ----------- | -------------------------------------------------------------------------- |
| `role`      | The job function of the agent (e.g., "Complaint Handler", "FAQ Assistant") |
| `goal`      | What the agent is expected to accomplish                                   |
| `backstory` | Background context and personality                                         |
| `llm`       | Language model powering the agent                                          |


### Example
``` python
from crewai import Agent

faq_agent = Agent(
    role="FAQ Assistant",
    goal="Provide quick and accurate responses to common customer queries",
    backstory="An expert in product knowledge and FAQs.",
    llm=llm
)
```
### Task
Each Task defines a unit of work assigned to a specific agent.

| Field             | Description                             |
| ----------------- | --------------------------------------- |
| `description`     | What the task is asking the agent to do |
| `expected_output` | Format/standard for the agent’s output  |
| `agent`           | Which agent will execute the task       |

### Example
``` python
from crewai import Task

faq_task = Task(
    description="Answer top 5 most asked customer questions from the past week.",
    expected_output="A markdown list of 5 questions with answers.",
    agent=faq_agent
)
```



