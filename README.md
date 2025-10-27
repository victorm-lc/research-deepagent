# Example DeepAgent

A research agent built with [DeepAgents](https://github.com/langchain-ai/deepagents) and LangGraph that conducts thorough research and writes polished reports.

## Features

- **Research Sub-Agent**: Conducts deep research on specific topics using internet search
- **Critique Sub-Agent**: Reviews and critiques draft reports for quality and completeness
- **Report Generation**: Creates comprehensive, well-structured research reports in markdown

## Installation

Install dependencies using [UV](https://docs.astral.sh/uv/):

```bash
uv sync
```

## Configuration

Set your Tavily API key as an environment variable:

```bash
export TAVILY_API_KEY="your-api-key-here"
```

You can get a Tavily API key at [tavily.com](https://tavily.com/).

## Running the Agent

Start the LangGraph development server:

```bash
langgraph dev
```

This will start:
- 🚀 API server at http://127.0.0.1:2024
- 🎨 Studio UI at https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024
- 📚 API docs at http://127.0.0.1:2024/docs

Open the Studio UI link in your browser to interact with the agent.

## How It Works

The agent orchestrates multiple specialized sub-agents:
1. Writes the research question to `question.txt`
2. Uses the research-agent to gather information on specific topics
3. Writes a draft report to `final_report.md`
4. Uses the critique-agent to review the report
5. Iterates on research and editing until satisfied with the final report