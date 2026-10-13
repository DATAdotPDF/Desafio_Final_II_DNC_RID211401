<p align="center">
 <img width="1584" height="396" alt="Generative AI Data Engineering Final Project Banner" src="https://github.com/user-attachments/assets/13a8cf3d-0703-4ccb-997d-9c294927d387" />
</p>

# 🤖 Generative AI for Fraud Detection – DNC

Final project for DNC's Data Engineering course, focused on **AI pattern detection**, **graph modeling**, **FastAPI**, and **analytical visualization with a generative agent**.

---

## 📋 Project Description

This project presents a **Generative AI** solution for automated operational data analysis.
The application identifies **fraud, inconsistencies, and errors** by dynamically and explainably combining multiple sources, including spreadsheets and CSV files.

**NetworkX** models the data as a graph of users, stores, and products connected by events.
These relationships are analyzed through **centrality**, **betweenness**, and **similarity** metrics to detect suspicious patterns.
The API was built with **FastAPI** and connects to a conversational AI agent that answers questions about data behavior.

---

## 📁 Project Structure

```bash
ia_generativa_dnc/
├── 00_documentos/       # Supporting documents and visuals
├── 01_base_de_dados/    # Original and processed CSV files
├── 02_modelagem/        # Graph modeling and creation scripts
├── 03_api/              # FastAPI code and endpoints
├── 04_agent/            # AI agent integration
├── 05_docker/           # docker-compose and dependencies
├── data/                # Intermediate Bronze/Silver/Gold data
├── notebooks/           # Prototyping and exploratory analysis
├── .env                 # Sensitive variables, not versioned
├── requirements.txt     # Project dependencies
└── README.md            # This file
```

---

## ⚙️ Technologies Used

- Python 3.11
- FastAPI – analytical API and project backend
- NetworkX – graph modeling and analysis
- Pandas – data cleaning and transformation
- Jupyter Notebook – prototyping and exploratory analysis
- Docker – environment containerization
- Git and GitHub – version control and documentation
- macOS Sonoma 14.6

---

## 🧠 AI Analytical Logic

The AI automatically combines different data sources to identify patterns such as:

1. Exchanges with more outgoing than incoming movements
2. Products that appear in both adjustments and exchanges
3. A low percentage of cash sales compared with the average
4. Exchange and cancellation percentages above the expected pattern
5. Suspicious movements within a short time interval
6. Customers and products that repeatedly appear in discrepancies

These insights are returned through the API in natural language by the generative agent.

---

## 🧩 Pipeline Stages

1. **Data collection:** read multiple CSV files for adjustments, returns, cancellations, and inventory.
2. **Cleaning and standardization:** convert types, remove nulls, and normalize columns.
3. **Integration and enrichment:** join datasets and create derived metrics.
4. **Graph modeling:** create entities and connections between operational events.
5. **Metric calculation:** compute degree centrality, betweenness, and connected components.
6. **API integration:** expose results through FastAPI.

---

## ✅ Run Locally

```bash
# Clone the repository
git clone https://github.com/DATAdotPDF/Desafio_Final_DNC_II.git
cd ia_generativa_dnc

# Create the virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Create the .env file with your variables
API_KEY=your_token
ENVIRONMENT=dev

# Run the API
uvicorn api.main:app --reload

# Open:
# http://localhost:8000/docs
# You can test the /construir_grafo endpoint with sample data.
```

---

## ☁️ Run with Docker

```bash
cd 05_docker

# Initialize the container
docker-compose up --build

# The API will be available at:
# http://localhost:8000

# Open notebooks through local Jupyter or VS Code connected to the container.
```

---

## 📊 Results

- **Central entities:** users and stores with the highest event volume
- **Key connectors:** operators that connect multiple flows
- **Coordinated activities:** event groups with repeated relationships

These results help identify suspicious patterns automatically and reduce manual analysis time while improving audit reliability.

---

## 🔐 Confidentiality and Security

- All data was anonymized, and sensitive folders are password protected.
- Access can be requested from the responsible team.
- Sensitive variables are stored in `.env`, which is ignored by Git.
- The project follows secure version control and access control practices.

---

## 📚 References and Links

- **Pedro's portfolio (PDF):** [Oscar Project (DNC)](https://datapedutraferreir.wixsite.com/pdfdata/projects/desafio-final-ii---dnc)
- **DNC Data School:** [https://www.escoladnc.com.br](https://www.escoladnc.com.br)
- **FastAPI documentation:** [https://fastapi.tiangolo.com/](https://fastapi.tiangolo.com/)
- **NetworkX:** [https://networkx.org/documentation/stable/](https://networkx.org/documentation/stable/)
- **Docker:** [https://www.docker.com/](https://www.docker.com/)
- **Python:** [https://www.python.org/](https://www.python.org/)

---

## 👥 Project Team

| Name | LinkedIn | GitHub |
|------|-----------|--------|
| **Pedro Ferreira (.pdf)** | [linkedin.com/in/datadotpdf](https://www.linkedin.com/in/datadotpdf) | [github.com/DATAdotPDF](https://github.com/DATAdotPDF) |
| **Guilherme Gabriel Souza** | [linkedin.com/in/guilhermegabsouza](https://www.linkedin.com/in/guilhermegabsouza) | [github.com/guigabz](https://github.com/guigabz) |
| **Bernardo Rodrigues Abelo** | [linkedin.com/in/bernardo-abelo-56b760236](https://www.linkedin.com/in/bernardo-abelo-56b760236/) | [github.com/bernardoabelo](https://github.com/bernardoabelo) |
| **Rodrigo Peres** | [linkedin.com/in/rodrigo-peres-ds](https://www.linkedin.com/in/rodrigo-peres-ds) | [github.com/engrperes](https://github.com/engrperes) |
| **Max Matsuya** | [linkedin.com/in/max-mitsuya](https://www.linkedin.com/in/max-mitsuya) | [github.com/maxMitsuya](https://github.com/maxMitsuya) |

---

> Project developed as the final assignment for the **DNC School Data Engineering course**,
> combining **generative AI, graph analysis, and data automation** in an integrated pipeline.