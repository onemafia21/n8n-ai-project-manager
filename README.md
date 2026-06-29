# n8n-ai-project-manager
An AI-powered n8n workflow that instantly transforms unstructured chat inputs into structured project roadmaps and syncs them to Google Sheets.

# 🤖 AI Project Manager Agent (n8n Workflow)

![n8n](https://img.shields.io/badge/n8n-FF6D5A?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-34A853?style=for-the-badge&logo=google-sheets&logoColor=white)

An intelligent automation workflow built in n8n that transforms unstructured chat messages into comprehensive, structured project roadmaps. By leveraging Generative AI and structured output parsing, this agent instantly breaks down high-level tasks into actionable milestones and assigns them to team members in a tracking spreadsheet.

## 🚀 Features

* **Natural Language Input:** Accepts unstructured project ideas via chat.
* **Intelligent Context Gathering:** Automatically retrieves employee/team data from a spreadsheet to make informed task assignments.
* **Generative AI Agent:** Utilizes an OpenAI Chat Model to act as a Project Manager, breaking down the main objective into logical phases.
* **Structured Output:** Forces the LLM to output precise JSON data (Milestone name, Description, Owner, Start/End Dates, Priority, Status).
* **Automated Data Entry:** Iterates through the generated milestones and appends them directly into a Google Sheet project tracker.

## 🧠 Workflow Architecture

The workflow consists of the following automated pipeline:

1. **When chat message received:** The trigger node capturing the user's prompt.
2. **Get row(s) in sheet:** Fetches current team/employee data (e.g., Roles, Departments) to give the AI context for assigning tasks.
3. **Aggregate:** Combines the team data and chat input for the AI Agent.
4. **AI Agent (OpenAI Chat Model + Structured Output Parser):** The core engine. It analyzes the request, references the employee context, and generates a structured array of milestones.
5. **Split Out:** Separates the array of milestones into individual items.
6. **Append row in sheet:** Writes each milestone as a new row in the project management tracker.

## 🎯 Example Use Case

**Input:**
> "I have a task of designing a new website for my client by December, the website is an e commerce website that features 500 products."

**Automated Output (Generated in < 10 seconds):**
The agent generated a 10-step roadmap and appended it to the sheet, including milestones like:
* *Project kickoff & discovery* (Owner: Priya Patel, Priority: Critical)
* *UX & information architecture* (Owner: Rohan Mehta, Priority: High)
* *Frontend development* (Owner: Neha Verma, Priority: High)
* *Backend & integrations* (Owner: Karan Singh, Priority: Critical)
* *Product data import & CMS setup* (Owner: Ananya Gupta, Priority: High)

## 📸 Screenshots

*(Add a screenshot of your n8n workflow canvas here)*
`![Workflow Image](link-to-your-image)`

*(Add a screenshot of the populated Google Sheet here)*
`![Spreadsheet Image](link-to-your-image)`

## 🛠️ How to Use This Workflow

1. Install [n8n](https://n8n.io/).
2. Download the `My_workflow.json` file from this repository.
3. In your n8n workspace, click **Add Workflow** -> **Import from File** and select the JSON file.
4. Authenticate your OpenAI and Google Sheets credentials within the respective nodes.
5. Map the Google Sheets nodes to your own spreadsheet documents.
6. Click **Test Workflow** or use the Chat interface to run the agent!

## 👨‍💻 Author

**Kshitij Gautre**
* Dedicated to building practical AI/ML applications, leveraging Generative LLMs, and driving enterprise automation. 
* [Connect with me on LinkedIn](Your-LinkedIn-URL)
