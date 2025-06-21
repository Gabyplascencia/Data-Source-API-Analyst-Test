# GitHub API – Data Source Analyst Test

This repository was developed as part of a technical assessment for the **Data Source API Analyst** position. The goal is to demonstrate the ability to interact with GitHub’s public REST API by:

- Searching for public repositories related to data analysis written in Python.
- Extracting detailed commit data from selected repositories.
- Accessing file content from public repositories using API endpoints.
- Documenting the methodology and outlining common challenges and their solutions.

---

##  Repository Structure
├── Content/
│ ├── github_api_documentation.md # Documentation of API endpoints used
│ └── troubleshooting.md # Guide to handle common API errors
│
├── Postman_Collection/
│ └── github_api_colab.ipynb # Jupyter Notebook (Google Colab) with analysis
│
├── README.md # This file

---

##  Instructions to Reproduce the Analysis

1. **Clone this repository**:
   ```bash
   git clone https://github.com/Gabyplascencia/Data-Source-API-Analyst-Test.git

2. Open the notebook github_api_colab.ipynb in Google Colab (recommended) or a local Jupyter Notebook environment.

3. **GitHub Authentication:**

- Upon execution, the notebook will prompt you to enter a GitHub Personal Access Token (PAT).

- The token is requested securely using Python’s getpass() function and is not stored.

- Do not hardcode your token into the notebook.

4. **Dependencies:**

The notebook relies on the requests library, which is pre-installed in Colab and most Jupyter setups.

If needed, install locally with:
        pip install requests

---

## Endpoints used

- Search public repositories: `/search/repositories`
- Get commits: `/repos/{owner}/{repo}/commits`
- Get content: `/repos/{owner}/{repo}/contents/{path}`

---

## Personal Reflection
This project allowed me to apply my skills in RESTful API integration, error handling, pagination, and secure authentication. I ensured all steps followed best practices in both coding and documentation, while maintaining a clear and organized repository structure.

Completing this task reinforced my ability to quickly adapt to technical requirements, build reproducible data workflows, and document solutions clearly. I am confident in my capacity to contribute effectively to a data-driven environment and to communicate technical insights in a professional and secure manner.

---

**Author:
- Gaby Rivera Plascencia

- github.com/Gabyplascencia
