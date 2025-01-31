# Assignment 1 - Document Processing Platform
 
## Project Links and Resources
 
- **GitHub Issues and Tasks**: [https://github.com/DAMG7245/Assignment01/issues]
- **Codelabs Documentation**: [https://codelabs-preview.appspot.com/?file_id=1SIXWV1sl0IVc_6BME22Uj84kIkyHPPOUMs0PCo3Rb_Y#6]
- **Project Submission Video (5 Minutes)**: []
- **Hosted Application Links**:
  - **Frontend (Streamlit)**: [http://24.199.83.132:8502/]
  - **Backend (FastAPI)**: [http://24.199.83.132:8000/]
 
## Introduction
 
This project focuses on building a **document processing platform** capable of extracting, structuring, and managing data from **unstructured sources like PDFs and web pages**. The goal is to evaluate the feasibility of **open-source and enterprise tools**, compare their performance, and develop a **Client-facing Streamlit application** that integrates document processing with **standardization, storage, and retrieval mechanisms**.  
 
The system will extract content from **PDFs and web pages**, process it into **Markdown format**, and store it efficiently in **AWS S3**. It will also provide a **FastAPI-based backend** and a **Streamlit-based frontend** for user interaction. The platform aims to ensure **scalability, security, and usability** by integrating modern technologies for **data extraction**.  
 
By leveraging **BeautifulSoup, Adobe PDF Services, Docling, and Jina.ai**, this project will evaluate various methodologies for document processing. Additionally, it will implement **FastAPI and Streamlit** to enable **secure access, document processing, and retrieval** via an interactive user interface.
 
 
The core technologies used in this project include:
- **PyMuPDF**: Used for PDF extraction as an Open Source Tool.
- **Adobe PDF Services**: Used for PDF extraction as an Closed Source Tool.
- **Jina.ai**: Used for Web Page extraction as an Closed source Tool.
- **Beautiful Soup**: Used for Web Page extraction as an Open Source Tool.
- **FastAPI**: Backend for handling requests.
- **Streamlit**: Frontend for the client-facing application.
- **Ocean Basket**: For Delopyment.
 
The project aims to provide a comprehensive platform for extracting, storing, and interacting with document data.
 
## Problem Statement
 
The challenge is to develop a **scalable platform** that enables users to:  
1. **Extract and convert** data from PDFs and web pages into a structured format.  
2. **Compare open-source and enterprise tools** for document processing efficiency.  
3. **Store and retrieve processed data** in AWS S3 with proper organization.  
4. **Provide an Client Interface** for seamless interaction.  
 
### **Desired Outcome:**  
- Efficient extraction and conversion of PDF and webpage data.  
- Standardized storage of processed content in **Markdown format**.  
- Scalable and well-organized infrastructure for storing and retrieving files in **AWS S3**.  
- A seamless **API and client interface** for processing and interacting with extracted data.  
 
### **Constraints:**  
- Handling large datasets efficiently from **PDFs and web pages**.  
- Managing **multiple tools for extraction** (open-source and enterprise).  
- Ensuring **proper organization and retrieval** of files in AWS S3.  
 
## **Proof of Concept**  
 
The project utilizes two main approaches for document extraction:  
- **PyMuPDF & Beautiful Soup** (open-source) and **Adobe PDF Services & Jina.ai** (enterprise).  
 
The extracted content is stored in **AWS S3** for efficient retrieval and further processing. Initial setup involved:  
- Developing Python Functions to handle the extraction of texts,tables,images from PDF's and WebPages.  
- Storing extracted content in **Markdown format**.  
- Organizing processed files in **AWS S3** with structured naming conventions and metadata tagging.  
- Developing an **API** to handle document processing and retrieval.  
- Creating a **client-facing Streamlit interface** for uploading and viewing extracted content.  
 
Challenges such as **handling diverse document structures and optimizing extraction accuracy** have been addressed by using multiple extraction tools and refining the standardization process.  
 
 
## Prerequisites
 
- Python 3.1 or higher
- Adobe PDF Services API credentials (client ID and client secret)
- Jina.ai API credentials (client ID and secret key)
- Docling 
- Git (for cloning the repository)
 
## Setup Instructions
 
## 1. Clone the Repository
```bash
git clone <repository-url>
cd <repository-name>
```
 
## 2. Set Up Python Virtual Environment
 
#### On Windows:
```bash
# Create virtual environment
python -m venv venv
 
# Activate virtual environment
venv\Scripts\activate
```
 
#### On macOS/Linux:
```bash
# Create virtual environment
python3 -m venv venv
 
# Activate virtual environment
source venv/bin/activate
```
 
## 3. Install Dependencies

### Install backend dependencies
```bash
pip install -r backend/requirements.txt
pip install -r enterprise_service/requirements.txt
pip install -r opensource_service/requirements.txt

### Install frontend dependencies
pip install -r frontend/requirements.txt

```
## 4. Configure Credentials in setup.h
 
Eg: Create a `.env` file in the project root and add your Adobe API credentials:
```plaintext
PDF_SERVICES_CLIENT_ID=your_client_id_here
PDF_SERVICES_CLIENT_SECRET=your_client_secret_here
```
 
## Usage

### 1. Activate the Virtual Environment
If not already activated, use the following commands:

```bash
# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 2. Run the Setup Script
Execute the setup script to install dependencies:

```bash
./setup.sh
```

### 3. Run the Backend Services
Start the backend services with:

```bash
python backend/main.py
python backend/enterprise_service/main.py
python opensource_service/main.py
```

### 4. Run the Frontend
Launch the frontend application:

```bash
streamlit run frontend/streamlit_app.py
```



## Project Directory Structure

```
DAMG7245_Assignment01/
│── backend/
│   ├── enterprise_service/
│   │   ├── utils/
│   │   │   ├── pdf_handler.py
│   │   │   ├── pdf_utils.py
│   │   │   ├── web_handler.py
│   │   │   ├── web_utils.py
│   │   ├── main.py
│   │   ├── requirements.txt
│
│── opensource_service/
│   ├── app/
│   │   ├── routes/
│   │   │   ├── pdf_routes.py
│   │   │   ├── web_handler_routes.py
│   │   │   ├── web_routes.py
│   │   ├── utils/
│   │   │   ├── pdf_utils.py
│   │   │   ├── web_handler.py
│   │   │   ├── web_utils.py
│   ├── logs/
│   │   ├── parsing.log
│   ├── main.py
│   ├── requirements.txt
│
│── frontend/
│   ├── pages/
│   ├── requirements.txt
│   ├── streamlit_app.py
│
│── docs/
│   ├── diagrams/
│   ├── random.txt
│   ├── AIUseDisclosure.md
│   ├── README.md
│
│── .gitignore
│── setup.sh
```


## Description of Project Directory

### Backend
- **`app/routers/`**: Contains API route handlers for file storage, PDF extraction, and web scraping.
- **`app/utils/`**: Houses configuration settings and helper functions.

### Enterprise Service
- **`app/routes/`**: Handles enterprise-level document processing, PDF extraction, and web scraping.
- **`app/utils/`**: Includes utilities for document handling and processing.
- **`main.py`**: Entry point for the enterprise service.

### Open Source Service
- **`app/routes/`**: API endpoints for open-source document handling.
- **`app/utils/`**: Utilities for PDF and web content processing.
- **`logs/parsing.log`**: Logs for debugging and tracking processing activities.
- **`main.py`**: Entry point for the open-source service.

### Frontend
- **`streamlit_app.py`**: Streamlit-based UI for user interaction.
- **`pages/`**: Contains different UI components.
- **`requirements.txt`**: Dependencies for running the frontend.

### Documentation
- **`docs/`**: Contains system diagrams and documentation files.
- **`README.md`**: Project description and setup guide.
- **`AIUseDisclosure.md`**: Disclosure related to AI usage in the project.

### Miscellaneous
- **`.gitignore`**: Specifies files to be ignored in version control.
- **`setup.sh`**: Script to set up dependencies and environments.


## Notes
 
- The virtual environment should be activated every time you work on the project
- Keep your Closed source credentials secure and never commit them to version control
- Make sure you have proper permissions for file operations in the project directory
 
## Troubleshooting
 
1. If you encounter permission errors, make sure you have write access to the output directory
 
2. For Enterprise tools errors, verify your credentials in the `.env` file
 
3. If pip install fails:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```
 
4. For virtual environment issues:
   ```bash
   # Remove existing venv
   rm -rf venv
   
   # Create new venv
   python -m venv venv
   ```
 
## Dependencies
 
- requests==2.31.0
- beautifulsoup4==4.12.2
- pandas==2.1.3
- markdown==3.5.1
- adobe-pdfservices-sdk
- openpyxl>=3.0.10
- pathlib>=1.0.1
- markdown-it-py>=2.0.0
- python-dotenv>=0.19.0
--
 
## Architecture Diagram
 
![Architecture Diagram]![image](https://github.com/user-attachments/assets/4a0291dd-ad83-4559-9089-91fcfa977f6d)

 
### **Description of Components**  
 
- **Digital Ocean**: The cloud platform where both the **FastAPI backend** and **Streamlit frontend** are deployed, making the application accessible online.  
 
- **Client Interface (Streamlit)**: A user-friendly web application where users can **upload PDFs**, **enter webpage URLs**, **select extraction tools**, and **view extracted data** in an interactive manner.  
 
- **Document Type Selection**: Allows users to choose between **PDF Extraction** and **Web Scraping**, determining which processing method will be used.  
 
- **Tool Selection**:  
  - **Web Scraping Tools**:  
    - **Enterprise (Jina.ai)** → AI-powered web scraping tool for structured and unstructured web data.  
    - **Open Source (Beautiful Soup)** → Python library for parsing and extracting data from HTML and XML documents.  
  - **PDF Extraction Tools**:  
    - **Enterprise (Adobe PDF Services)** → Proprietary tool for extracting text, tables, and images from PDFs.  
    - **Open Source (PyMuPDF)** → Open-source tool for document processing, supporting text and image extraction.  
 
- **FastAPI Server (Backend Processing)**: Handles user requests, processes extracted content, and sends structured data for storage and retrieval.  
 
- **Processing Extracted Data**:  
  - Extracts **text, tables, and images** from PDFs and webpages.  
  - Converts extracted content into **Markdown format** for standardization.  
  - Sends extracted images and references to **AWS S3**.  
 
- **Markdown Format Storage**: Stores extracted and structured **text content** , making it easy to query and retrieve processed data.  
 
- **AWS S3 (Images & References)**: Stores extracted **images, tables, and metadata** for future access and retrieval.  
 
### **Data Flow:**  
1. **Users upload PDFs or enter webpage URLs** through the **Streamlit client interface**.  
2. **Users select the extraction type** → **PDF Extraction or Web Scraping**.  
3. **Users choose an extraction tool** → **Open-source (PyMuPDF, Beautiful Soup) or Enterprise (Adobe PDF Services, Jina.ai)**.  
4. **The FastAPI backend processes the request**, extracting **text, tables, and images** from the selected document.  
5. **Extracted data is converted into Markdown format** for standardization.  
6. **Extracted images and references are stored in AWS S3**
7. **Users interact with the extracted content** through the **Streamlit interface**, viewing and downloading processed documents.  
 
 
**Team Members:**
- Sai Priya Veerabomma - 33.3% (Backend,Frontend)
- Sai Srunith Silvery - 33.3% (Backend,Frontend)
- Vishal Prasanna - 33.3% (Deployment,Backend)

## References
 
- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [Streamlit Documentation](https://docs.streamlit.io/)
- [Docling](https://ds4sd.github.io/docling/)
- [Jina.ai](https://jina.ai/serve/)
- [Adobe PDF Services](https://developer.adobe.com/document-services/docs/overview/)
- [PyMuPDF] (https://pymupdf.readthedocs.io/en/latest/tutorial.html)
 
## Contributing
- Follow the repository structure and coding guidelines.
- Submit pull requests with detailed commit messages.
- Report issues or suggest enhancements through GitHub issues.

## License
This project is open-source and follows a MIT licensing model. See `LICENSE` for more details.
