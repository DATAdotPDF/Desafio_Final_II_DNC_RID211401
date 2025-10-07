<p align="center">
 <img width="1584" height="396" alt="DESAFIO FINAL II ENG DADOS_BANNER" src="https://github.com/user-attachments/assets/13a8cf3d-0703-4ccb-997d-9c294927d387" />
</p>

# 🤖 IA Generativa para Detecção de Fraudes – DNC

Projeto final do curso de Engenharia de Dados da DNC, desenvolvido no macOS, com foco em **detecção de padrões com IA**, **modelagem em grafos**, **API com FastAPI** e **visualização analítica com agente generativo**.

---

## 📋 Descrição do Projeto

Este projeto apresenta uma solução de **IA Generativa** voltada à análise automatizada de dados operacionais.  
A aplicação identifica **fraudes, inconsistências e erros**, cruzando informações de múltiplas fontes (planilhas e CSVs) de forma dinâmica e explicável.  

A modelagem é feita com **NetworkX**, que estrutura os dados como um grafo de entidades (usuários, lojas e produtos) conectadas por eventos.  
Essas relações são analisadas por métricas de **centralidade**, **intermediação** e **similaridade** para detectar padrões suspeitos.  
A API foi construída em **FastAPI**, integrando-se a um agente conversacional de IA capaz de responder perguntas sobre o comportamento dos dados.

---

## 📁 Estrutura do Projeto

```bash
ia_generativa_dnc/
├── 00_documentos/       # Documentos de apoio e visuais
├── 01_base_de_dados/    # Arquivos CSV originais e tratados
├── 02_modelagem/        # Scripts de modelagem e criação de grafos
├── 03_api/              # Código da API FastAPI e endpoints
├── 04_agent/            # Integração com o agente de IA
├── 05_docker/           # docker-compose e dependências
├── data/                # Bases intermediárias (Bronze/Silver/Gold)
├── notebooks/           # Prototipagem e análises exploratórias
├── .env                 # Variáveis sensíveis (não versionadas)
├── requirements.txt     # Dependências do projeto
└── README.md            # Este arquivo
```

---

## ⚙️ Tecnologias Utilizadas
- Python 3.11  
- FastAPI – API analítica e backend do projeto  
- NetworkX – Modelagem e análise de grafos  
- Pandas – Limpeza e transformação dos dados  
- Jupyter Notebook – Prototipagem e análise exploratória  
- Docker – Containerização do ambiente  
- Git & GitHub – Versionamento e documentação  
- macOS Sonoma (14.6)

---

## 🧠 Lógica Analítica da IA

A IA realiza cruzamentos automáticos entre diferentes fontes de dados para identificar padrões como:

1. Trocas com mais saídas do que entradas  
2. Produtos presentes simultaneamente em ajustes e trocas  
3. Baixo percentual de vendas à vista comparado à média  
4. Percentuais de trocas e cancelamentos acima do padrão  
5. Movimentações suspeitas em curto intervalo de tempo  
6. Clientes e produtos reincidentes em divergências  

Esses insights são retornados via API em linguagem natural por meio do agente generativo.

---

## 🧩 Etapas do Pipeline

1. Coleta dos Dados – Leitura de múltiplos arquivos CSV (ajustes, devoluções, cancelamentos e inventário).  
2. Limpeza e Padronização – Conversão de tipos, remoção de nulos e normalização de colunas.  
3. Integração e Enriquecimento – União das bases e criação de métricas derivadas.  
4. Modelagem em Grafos – Criação das entidades e conexões entre eventos operacionais.  
5. Cálculo de Métricas – Centralidade de Grau, Intermediação e Componentes Conectados.  
6. Integração via API – Exposição dos resultados por meio da FastAPI.

---

## ✅ Como Executar Localmente

# Clone o repositório
git clone https://github.com/DATAdotPDF/Desafio_Final_DNC_II.git
cd ia_generativa_dnc

# Crie o ambiente virtual
python3 -m venv venv
source venv/bin/activate

# Instale as dependências
pip install -r requirements.txt

# Crie o arquivo .env com suas variáveis
API_KEY=seu_token
ENVIRONMENT=dev

# Execute a API
uvicorn api.main:app --reload

# Acesse:
# http://localhost:8000/docs
# Você poderá testar o endpoint /construir_grafo enviando dados de exemplo.

---

## ☁️ Execução com Docker

cd 05_docker

# Inicialize o container
docker-compose up --build

# A API estará disponível em:
# http://localhost:8000

# Os notebooks podem ser acessados via Jupyter local ou VSCode conectado ao container.

---

## 📊 Resultados Obtidos

- Entidades Centrais: usuários e lojas com maior volume de eventos  
- Conectores-Chave: operadores que conectam múltiplos fluxos  
- Atividades Coordenadas: grupos de eventos com relações repetitivas  

Esses resultados permitem identificar padrões suspeitos de forma automatizada,
reduzindo o tempo de análise manual e aumentando a confiabilidade das auditorias.

---

## 🔐 Confidencialidade e Segurança

- Todos os dados foram anonimizados e pastas com senhas (em caso de necessidade de acesso entrar em contato) 
- Variáveis sensíveis são armazenadas no arquivo .env (ignorado no Git).  
- O projeto segue práticas seguras de versionamento e controle de acesso.

---

## 📚 Referências & Links

- Portifolio Pedro (Projeto): https://datapedutraferreir.wixsite.com/pdfdata/projects/desafio-final-ii---dnc
- DNC Escola de Dados: https://www.escoladnc.com.br  
- FastAPI Documentation: https://fastapi.tiangolo.com/  
- NetworkX: https://networkx.org/documentation/stable/  
- Docker: https://www.docker.com/  
- Python: https://www.python.org/

---

Desenvolvido por Pedro Ferreira – LinkedIn: https://www.linkedin.com/in/datadotpdf

