# {{crew_name}} Crew

Welcome to the {{crew_name}} Crew project, powered by [crewAI](https://crewai.com). This template is designed to help you set up a multi-agent AI system with ease, leveraging the powerful and flexible framework provided by crewAI. Our goal is to enable your agents to collaborate effectively on complex tasks, maximizing their collective intelligence and capabilities.

## Installation

Ensure you have Python >=3.10 <=3.13 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management and package handling, offering a seamless setup and execution experience.

First, if you haven't already, install uv:

```bash
pip install uv
```

Next, navigate to your project directory and install the dependencies:

(Optional) Lock the dependencies and install them by using the CLI command:
```bash
crewai install
```

`pyproject.toml` lists everything the flow imports beyond crewAI: `agentops` (capped below 0.4, because `kickoff()` uses the 0.3 session API and `@record_tool`), `pydub` for chunking the audio (plus `audioop-lts` on Python 3.13), and the Google client libraries and `markdown` for the Gmail draft tool. The Gmail tool expects an OAuth client file at `src/meeting_minutes/crews/gmailcrew/tools/credentials.json`, and the `.env` needs `AGENTOPS_API_KEY`, `GMAIL_SENDER` and `GMAIL_RECIPIENT`.

### Customizing

**Add your `OPENAI_API_KEY` into the `.env` file**

The flow transcribes `src/meeting_minutes/EarningsCall.wav` in one-minute chunks with OpenAI `gpt-transcribe` ($0.0045/min). It used `whisper-1`, which OpenAI removes from the API on 2027-02-26 ([deprecations](https://developers.openai.com/api/docs/deprecations)).

- Modify `src/meeting_minutes/config/agents.yaml` to define your agents
- Modify `src/meeting_minutes/config/tasks.yaml` to define your tasks
- Modify `src/meeting_minutes/crew.py` to add your own logic, tools and specific args
- Modify `src/meeting_minutes/main.py` to add custom inputs for your agents and tasks

## Running the Project

To kickstart your crew of AI agents and begin task execution, run this from the root folder of your project:

```bash
crewai run
```

This command initializes the meeting-minutes Crew, assembling the agents and assigning them tasks as defined in your configuration.

This example, unmodified, will run the create a `report.md` file with the output of a research on LLMs in the root folder.

## Understanding Your Crew

The meeting-minutes Crew is composed of multiple AI agents, each with unique roles, goals, and tools. These agents collaborate on a series of tasks, defined in `config/tasks.yaml`, leveraging their collective skills to achieve complex objectives. The `config/agents.yaml` file outlines the capabilities and configurations of each agent in your crew.

## Support

For support, questions, or feedback regarding the {{crew_name}} Crew or crewAI.

- Visit our [documentation](https://docs.crewai.com)
- Reach out to us through our [GitHub repository](https://github.com/joaomdmoura/crewai)
- [Join our Discord](https://discord.com/invite/X4JWnZnxPb)
- [Chat with our docs](https://chatg.pt/DWjSBZn)

Let's create wonders together with the power and simplicity of crewAI.
