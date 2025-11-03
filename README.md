# Auto Email Assistant with CrewAI

**Auto Email Assistant with CrewAI** is a Python automation tool that automatically monitors your Gmail inbox and drafts responses for new emails. This project leverages **CrewAI**, **LangGraph**, and **LangChain Community** to streamline email management.

---

## Features

- Periodically checks your Gmail account for new emails.
- Skips previously checked emails to avoid duplicates.
- Drafts responses based on email content using `EmailFilterCrew`.
- Workflow loop runs at a configurable interval (default: 180 seconds).
- Easily customizable and extendable.

---

## Installation

### 1. Clone the repository
```bash
git clone https://github.com/username/auto-email-assistant-with-crewai.git
cd auto-email-assistant-with-crewai
```
### 2. Set up Python environment
```bash
python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows
```
### 3. Install dependencies
If using UV:
```bash
uv sync
```
Or with pip:
```bash
pip install -r requirements.txt
```
### 4. Set up Gmail API credentials and .env file
Create a .env file:
```bash
MY_EMAIL=your_email@gmail.com
GOOGLE_APPLICATION_CREDENTIALS=credentials.json
Obtain credentials.json from Google Cloud Console.
```
### Usage
Run the project:
```BASH
python main.py
```
Terminal output will show workflow logs:

```BASH
# Checking for new emails
## No new emails
## Waiting for 180 seconds
The workflow checks for new emails every 180 seconds by default.
```
### Key Components
```bash
./src/graph.py – Class defining the workflow nodes and edges.

./src/nodes.py – Class containing the functions for each node.

./src/state.py – State declaration for the workflow.

./src/crew/agents.py – Class defining the CrewAI Agents.

./src/crew/tasks.py – Class defining the CrewAI Tasks.

./src/crew/crew.py – Class defining the CrewAI Crew.

./src/crew/tools.py – Class implementing the GmailDraft Tool.
```
### Customization
Customize email filtering and draft logic in src/nodes.py.

Modify workflow parameters and wait time in src/graph.py.

## Project Structure
```bash
auto-email-assistant-with-crewai/
├── src/
│   ├── graph.py
│   ├── nodes.py
│   ├── state.py
│   └── crew/
│       ├── agents.py
│       ├── tasks.py
│       ├── crew.py
│       └── tools.py
├── main.py
├── pyproject.toml
├── requirements.txt
├── README.md
└── .env (local, secret)
```
## License
This project is licensed under the MIT License.
