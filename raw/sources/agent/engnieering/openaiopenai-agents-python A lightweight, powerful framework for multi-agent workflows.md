---
title: "openai/openai-agents-python: A lightweight, powerful framework for multi-agent workflows"
source: "https://github.com/openai/openai-agents-python"
author:
published:
created: 2026-04-23
description: "A lightweight, powerful framework for multi-agent workflows - openai/openai-agents-python"
tags:
  - "agent"
---
## OpenAI Agents SDK

The OpenAI Agents SDK is a lightweight yet powerful framework for building multi-agent workflows. It is provider-agnostic, supporting the OpenAI Responses and Chat Completions APIs, as well as 100+ other LLMs.

[![Image of the Agents Tracing UI](https://camo.githubusercontent.com/161e058e913301d37f41ce953af676421deb4ad764cbeabaab37430ceabb59ee/68747470733a2f2f63646e2e6f70656e61692e636f6d2f4150492f646f63732f696d616765732f6f726368657374726174696f6e2e706e67)](https://camo.githubusercontent.com/161e058e913301d37f41ce953af676421deb4ad764cbeabaab37430ceabb59ee/68747470733a2f2f63646e2e6f70656e61692e636f6d2f4150492f646f63732f696d616765732f6f726368657374726174696f6e2e706e67)

> [!note] Note
> Looking for the JavaScript/TypeScript version? Check out [Agents SDK JS/TS](https://github.com/openai/openai-agents-js).

### Core concepts:

1. [**Agents**](https://openai.github.io/openai-agents-python/agents): LLMs configured with instructions, tools, guardrails, and handoffs
2. [**Sandbox Agents**](https://openai.github.io/openai-agents-python/sandbox_agents): Agents preconfigured to work with a container to perform work over long time horizons.
3. **[Agents as tools](https://openai.github.io/openai-agents-python/tools/#agents-as-tools) / [Handoffs](https://openai.github.io/openai-agents-python/handoffs/)**: Delegating to other agents for specific tasks
4. [**Tools**](https://openai.github.io/openai-agents-python/tools/): Various Tools let agents take actions (functions, MCP, hosted tools)
5. [**Guardrails**](https://openai.github.io/openai-agents-python/guardrails/): Configurable safety checks for input and output validation
6. [**Human in the loop**](https://openai.github.io/openai-agents-python/human_in_the_loop/): Built-in mechanisms for involving humans across agent runs
7. [**Sessions**](https://openai.github.io/openai-agents-python/sessions/): Automatic conversation history management across agent runs
8. [**Tracing**](https://openai.github.io/openai-agents-python/tracing/): Built-in tracking of agent runs, allowing you to view, debug and optimize your workflows
9. [**Realtime Agents**](https://openai.github.io/openai-agents-python/realtime/quickstart/): Build powerful voice agents with `gpt-realtime-1.5` and full agent features

Explore the [examples](https://github.com/openai/openai-agents-python/tree/main/examples) directory to see the SDK in action, and read our [documentation](https://openai.github.io/openai-agents-python/) for more details.

## Get started

To get started, set up your Python environment (Python 3.10 or newer required), and then install OpenAI Agents SDK package.

### venv

```
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install openai-agents
```

For voice support, install with the optional `voice` group: `pip install 'openai-agents[voice]'`. For Redis session support, install with the optional `redis` group: `pip install 'openai-agents[redis]'`.

### uv

If you're familiar with [uv](https://docs.astral.sh/uv/), installing the package would be even easier:

```
uv init
uv add openai-agents
```

For voice support, install with the optional `voice` group: `uv add 'openai-agents[voice]'`. For Redis session support, install with the optional `redis` group: `uv add 'openai-agents[redis]'`.

## Run your first Sandbox Agent

[Sandbox Agents](https://openai.github.io/openai-agents-python/sandbox_agents) are new in version 0.14.0. A sandbox agent is an agent that uses a computer environment to perform real work with a filesystem, in an environment you configure and control. Sandbox agents are useful when the agent needs to inspect files, run commands, apply patches, or carry workspace state across longer tasks.

```
from agents import Runner
from agents.run import RunConfig
from agents.sandbox import Manifest, SandboxAgent, SandboxRunConfig
from agents.sandbox.entries import GitRepo
from agents.sandbox.sandboxes import UnixLocalSandboxClient

agent = SandboxAgent(
    name="Workspace Assistant",
    instructions="Inspect the sandbox workspace before answering.",
    default_manifest=Manifest(
        entries={
            "repo": GitRepo(repo="openai/openai-agents-python", ref="main"),
        }
    ),
)

result = Runner.run_sync(
    agent,
    "Inspect the repo README and summarize what this project does.",
    # Run this agent on the local filesystem
    run_config=RunConfig(sandbox=SandboxRunConfig(client=UnixLocalSandboxClient())),
)
print(result.final_output)

# This project provides a Python SDK for building multi-agent workflows.
```

(*If running this, ensure you set the `OPENAI_API_KEY` environment variable*)

(*For Jupyter notebook users, see [hello\_world\_jupyter.ipynb](https://github.com/openai/openai-agents-python/blob/main/examples/basic/hello_world_jupyter.ipynb)*)

Explore the [examples](https://github.com/openai/openai-agents-python/tree/main/examples) directory to see the SDK in action, and read our [documentation](https://openai.github.io/openai-agents-python/) for more details.

## Acknowledgements

We'd like to acknowledge the excellent work of the open-source community, especially:

- [Pydantic](https://docs.pydantic.dev/latest/)
- [Requests](https://github.com/psf/requests)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [Griffe](https://github.com/mkdocstrings/griffe)

This library has these optional dependencies:

- [websockets](https://github.com/python-websockets/websockets)
- [SQLAlchemy](https://github.com/sqlalchemy/sqlalchemy)
- [any-llm](https://github.com/mozilla-ai/any-llm) and [LiteLLM](https://github.com/BerriAI/litellm)

We also rely on the following tools to manage the project:

- [uv](https://github.com/astral-sh/uv) and [ruff](https://github.com/astral-sh/ruff)
- [mypy](https://github.com/python/mypy) and [Pyright](https://github.com/microsoft/pyright)
- [pytest](https://github.com/pytest-dev/pytest) and [Coverage.py](https://github.com/coveragepy/coveragepy)
- [MkDocs](https://github.com/squidfunk/mkdocs-material)

We're committed to continuing to build the Agents SDK as an open source framework so others in the community can expand on our approach.