# Tools and Frameworks

## LangChain

A Python framework for building applications around LLMs. It supports tool usage, memory, chains of reasoning, and agent interfaces. LangChain provides the building blocks to combine language models with external data and APIs.

It is used to build a chain of actions to be performed in order (linear workflows or DAGs).

## LangGraph

A framework for building multi-agent workflows using a graph-based execution model. It allows you to define agents as nodes and their interactions as edges, ideal for orchestrating collaborative agents in Agentic AI.

Used for building stateful, multi-agent applications, and designed to be low-level and flexible.

### Core Components

#### Nodes

Individual steps or functions that do the actual computation.
Each node should perform a single, clear task.

- **Processing Nodes**: data transformation or computation.
- **Validation Nodes**: conditions or data integrity.
- **Integration Nodes**: interface with external systems.
- **Decision Nodes**: workflow paths based on conditions.

#### Edges

Degines how the execution flows.

#### State

Remembers everything across all the nodes.

### Capabilities

1. **Looping and branching**: make dynamic decisions on the go.
2. **State persistence**: maintains context over long interactions.
3. **Human-in-the-loop**: intervene when needed.
4. **Time travel**: rewind to previous states.

## LangChain vs LangGraph

### Features

|**Feature**                 |**LangChain**   |**LangGraph**   |
|------------------------|---|---|
|**Type**                    |  LLM orchestration framework based on chains and agents. |AI agent orchestration framework based on stateful graphs.   |
|**Workflow Structure**      |  Linear/DAG workflows (sequence of steps with no cycles). Good for "prompt → model → output” flows | Graph-based workflows (nodes and edges allow loops, branches, and dynamic transitions). Suited for complex flows.  |
|**State Management**       | Implicit/pass-through data. Chains carry inputs forward, but long-term state is limited by default  | Explicit global state ("memory bank") that all agents access. State is persistently stored and updated at each step.  |
|**Task Complexity**      |Best for simple to medium tasks: chatbots, RAG pipelines, sequential reasoning. | Designed for complex, multi-step tasks and workflows that evolve over time (for example, multi-agent assistants).  |
|**Agents and Collaboration**|Typically single-agent or linear chain; agents operate independently without inter-communication.  | Multi-agent. Agents (nodes) can call each other using the graph, share memory, or be arranged hierarchically.  |

### LangChain or LangGraph? When to use which

| Use Case | Use LangChain When... | Use LangGraph When... |
| :--- | :--- | :--- |
| **Workflow Complexity** | You have a clearly-defined, linear workflow. | You need complex workflows with branching logic or conditional steps. |
| **Development Speed** | You want to build something quickly—ideal for prototyping and MVPs. | You're building a production-grade system where reliability, traceability, and durability are essential. |
| **Memory Requirements** | Stateless or **light memory** needs (for example, current conversation only). | Long-term memory is needed across interactions or agents (for example, remembering context across sessions). |
| **Interaction Style** | Simple LLM tool use (for example, retrieval, transformation, response). | Multi-turn or human-in-the-loop interactions requiring persistent state and coordination. |
| **System Design** | Linear pipelines such as document Q&A, summarization, or format conversion. | Multi-agent architectures, process automation, or workflows with retries, dependencies, or approvals. |
| **Team Collaboration** | Individual developer exploring LLM capabilities quickly. | Teams designing modular, orchestrated systems with accountability and version control. |
