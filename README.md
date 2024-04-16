
# Setting up Ready2DeployRAG4OrgAtScale

## Prerequisites
- Python (version 3.7 or higher)
- Node.js (version 12 or higher)
- Git

## Step 1: Clone the Repository
git clone https://github.com/truefoundry/cognita.git

## Step 2: Create and Activate a Virtual Environment
cd <Project_root_directory>
python -m venv Ready2DeployRAG4OrgAtScale

# Activate the virtual environment:
# On Windows:
Ready2DeployRAG4OrgAtScale\Scripts\activate

# On Unix or MacOS:
source Ready2DeployRAG4OrgAtScale/bin/activate

## Step 3: Start the Backend Server
(Ready2DeployRAG4OrgAtScale) ~\PycharmProjects\Ready2DeployRAG4OrgAtScale\cognita>
uvicorn --host 0.0.0.0 --port 8000 backend.server.app:app --reload

## Step 4: Install Yarn
npm install -g yarn@1.22.19

## Step 5: Set up the Frontend
git clone https://github.com/truefoundry/docs-qa-playground.git
cd docs-qa-playground/frontend
yarn install
cp .env.example .env

# Open the `.env` file and ensure that the following configuration is set:
VITE_QA_FOUNDRY_URL=http://localhost:8000
VITE_DOCS_QA_DELETE_COLLECTIONS=false
VITE_DOCS_QA_STANDALONE_PATH=/
VITE_DOCS_QA_ENABLE_REDIRECT=false
VITE_DOCS_QA_MAX_UPLOAD_SIZE_MB=200

yarn dev
