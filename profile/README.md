# askTRACE Insight Platform

![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![GKE](https://img.shields.io/badge/GKE-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Amazon Web Services](https://img.shields.io/badge/Amazon%20Web%20Services-232F3E.svg?style=for-the-badge&logo=Amazon-Web-Services&logoColor=white)
![K8s Operator](https://img.shields.io/badge/K8s_Operator-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apache-kafka&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Groovy](https://img.shields.io/badge/Groovy-4298B8?style=for-the-badge&logo=apache-groovy&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF.svg?style=for-the-badge&logo=GitHub-Actions&logoColor=white)
![CI/CD](https://img.shields.io/badge/CI%2FCD-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Flyway](https://img.shields.io/badge/Flyway-CC0200?style=for-the-badge&logo=flyway&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?style=for-the-badge&logo=google&logoColor=white)
![AI](https://img.shields.io/badge/Artificial_Intelligence-FF6F00?style=for-the-badge&logo=openai&logoColor=white)

A comprehensive platform for processing, analyzing, and extracting insights from TRACE survey data using AI and cloud-native technologies.

## Project Overview

The askTRACE Insight Platform is an end-to-end system designed to transform the way educational institutions process and analyze Teacher Rating And Course Evaluation (TRACE) surveys. By leveraging modern cloud-native technologies and artificial intelligence, the platform enables educators, administrators, and decision-makers to:

- **Streamline Survey Processing**: Automate the extraction of structured data from PDF surveys
- **Centralize Data Management**: Securely store and organize survey data across courses and semesters
- **Generate AI-Powered Insights**: Use natural language queries to explore survey feedback
- **Make Data-Driven Decisions**: Identify trends and patterns in teaching effectiveness
- **Secure Sensitive Information**: Protect student feedback with enterprise-grade security

The platform implements a microservices architecture deployed on Kubernetes, with each component designed for scalability, reliability, and maintainability.

## Why askTRACE Insight Platform?

Educational institutions collect valuable feedback through course evaluations, but often struggle to efficiently process and extract actionable insights from this data. Traditional methods involve manual review of individual PDF surveys, making it difficult to:

1. **Scale Analysis**: As institutions grow, manually processing thousands of surveys becomes impractical
2. **Identify Patterns**: Without aggregated data, spotting trends across courses or departments is challenging
3. **Extract Qualitative Insights**: Free-text comments contain rich feedback that's difficult to systematically analyze
4. **Make Timely Improvements**: Delayed processing means feedback often can't inform immediate changes

The askTRACE Insight Platform solves these challenges by:

- Automating PDF data extraction using specialized processing techniques
- Storing structured data in a queryable database with proper relationships
- Transforming text data into semantic vector embeddings for similarity search
- Providing natural language query capabilities through integration with Google's Gemini AI
- Securing the entire pipeline with enterprise-grade authentication and authorization

This enables institutions to transform raw survey data into actionable insights that improve teaching effectiveness and student outcomes.

## System Architecture

![askTRACE System Architecture](https://github.com/cyse7125-sp25-team03/.github/blob/main/askTRACE-architecture.png)

The askTRACE Insight Platform consists of several interconnected components:

### User-Facing Interfaces
- **Web Application** (`trace-frontend`): React-based interface for managing courses, instructors, and surveys
- **Natural Language Interface** (`trace-llm-frontend`): ChatGPT-like interface for querying survey data using natural language

### Core Backend Services
- **API Server** (`api-server`): Go-based REST API for core platform functionality
- **PDF Processor** (`trace-processor`): Python service that extracts structured data from TRACE survey PDFs
- **Database Consumer** (`trace-consumer`): Service that stores processed survey data in PostgreSQL
- **Embedding Service** (`embedding-service`): Creates vector embeddings for semantic search capabilities
- **Natural Language Backend** (`trace-llm`): Connects to Google Gemini to answer natural language queries about TRACE data

### Infrastructure Components
- **Database Backup Operator** (`db-backup-operator`): Kubernetes operator for automated database backups
- **Helm Charts** (`helm-charts`): Kubernetes deployment configurations for all services
- **Infrastructure as Code** (`tf-gcp-infra`): Terraform configurations for GCP infrastructure
- **Jenkins Infrastructure** (`infra-jenkins`): Terraform code for provisioning Jenkins CI/CD server
- **Jenkins AMI Builder** (`ami-jenkins`): Packer templates for creating pre-configured Jenkins AMI
- **Database Migrations** (`db-trace-processor`): Database schema definitions and Flyway migration scripts

### Infrastructure Services
- **Apache Kafka**: Message broker for asynchronous communication between services
- **PostgreSQL**: Relational database for storing structured survey data
- **Google Cloud Storage**: Object storage for PDFs and database backups
- **Google Kubernetes Engine**: Managed Kubernetes for container orchestration
- **Google Gemini**: AI model for natural language processing and query answering

## Key Features

- **Secure User Authentication**: Role-based access control for administrators and educators
- **Course and Instructor Management**: Create, update, and organize courses and instructors
- **PDF Survey Upload and Processing**: Submit surveys and automatically extract structured data
- **AI-Powered Search**: Query survey data using natural language questions
- **Vector Similarity Search**: Find similar feedback across courses and semesters
- **Automated Database Backups**: Scheduled backups to Google Cloud Storage
- **Scalable Microservices Architecture**: Independently scalable components for handling varying loads
- **Cloud-Native Deployment**: Kubernetes-based deployment with infrastructure as code

## Repositories

| Repository | Description |
|------------|-------------|
| [api-server](https://github.com/cyse7125-sp25-team03/api-server.git) | Core REST API service for TRACE data management |
| [trace-processor](https://github.com/cyse7125-sp25-team03/trace-processor.git) | Service for extracting data from survey PDFs |
| [trace-consumer](https://github.com/cyse7125-sp25-team03/trace-consumer.git) | Service for consuming and storing processed survey data |
| [embedding-service](https://github.com/cyse7125-sp25-team03/embedding-service.git) | Service for generating vector embeddings from text data |
| [trace-llm](https://github.com/cyse7125-sp25-team03/trace-llm.git) | Service for processing natural language queries with Gemini |
| [db-backup-operator](https://github.com/cyse7125-sp25-team03/db-backup-operator.git) | Kubernetes operator for automated database backups |
| [trace-frontend](https://github.com/cyse7125-sp25-team03/trace-frontend.git) | React web application for TRACE data management |
| [trace-llm-frontend](https://github.com/cyse7125-sp25-team03/trace-llm-frontend.git) | Chat interface for natural language queries |
| [helm-charts](https://github.com/cyse7125-sp25-team03/helm-charts.git) | Helm charts for Kubernetes deployment |
| [tf-gcp-infra](https://github.com/cyse7125-sp25-team03/tf-gcp-infra.git) | Terraform configurations for GCP infrastructure |
| [db-trace-processor](https://github.com/cyse7125-sp25-team03/db-trace-processor.git) | Database schema and migration scripts |
| [infra-jenkins](https://github.com/cyse7125-sp25-team03/infra-jenkins.git) | Infrastructure as code for Jenkins CI/CD server |
| [ami-jenkins](https://github.com/cyse7125-sp25-team03/ami-jenkins.git) | Packer templates for building Jenkins AMI |

<!--
## Screenshots & Demos

### Web Application
![Web Dashboard](screenshots/dashboard.png)

### Course Management
![Course Management](screenshots/course-management.png)

### PDF Processing
![PDF Processing](screenshots/pdf-processing.png)

### Natural Language Query Interface
![Query Interface](screenshots/query-interface.png)

### Video Demo
[![Video Demo](https://img.youtube.com/vi/YOUTUBE_VIDEO_ID/0.jpg)](https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID)
-->

## Technologies Used

### Backend
- **Go**: For the API server implementation
- **Python**: For data processing and ML components
- **PostgreSQL**: Relational database
- **pgvector**: Vector extension for PostgreSQL
- **Apache Kafka**: Event streaming platform
- **Google Gemini**: AI language model
- **SentenceTransformers**: For generating vector embeddings

### Frontend
- **React**: UI library
- **TypeScript**: Type-safe JavaScript
- **Material UI**: Component library
- **Vite**: Build tool
- **Axios**: HTTP client

### Infrastructure
- **Google Cloud Platform**: Cloud provider
- **Google Kubernetes Engine**: Managed Kubernetes
- **Terraform**: Infrastructure as code
- **Helm**: Kubernetes package manager
- **Docker**: Containerization
- **Istio**: Service mesh
- **cert-manager**: Certificate management

## Getting Started

For detailed setup instructions, please refer to the [helm-charts](https://github.com/cyse7125-sp25-team03/helm-charts.git) repository, which contains deployment configurations for all components.

### Prerequisites
- Google Cloud Platform account
- kubectl, helm, and terraform installed
- Docker for local development

### Deployment Overview
1. Set up GCP infrastructure using Terraform
2. Deploy core services using Helm charts
3. Configure ingress and SSL certificates
4. Set up required secrets for database and API connections

## Contributors

- [Sohan Patil](https://github.com/roarceus) [![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github)](https://github.com/roarceus) [![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/sohanpatil98/)
- [Aakanksha Desai](https://github.com/aakanksha-arun) [![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github)](https://github.com/aakanksha-arun) [![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/desaiaakanksha8/)

## Mentors

- [Tejas Parikh](https://www.linkedin.com/in/tejassunilparikh/) [![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/tejassunilparikh/)
- [Vinay Chelpuri](https://www.linkedin.com/in/vinaychelpuri/) [![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/vinaychelpuri/)

## License

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](https://github.com/cyse7125-sp25-team03/.github/blob/main/LICENSE) file for details.

## Acknowledgments

- Northeastern University CSYE7125 - Advanced Cloud Computing Program
- The open-source community for the amazing tools and libraries that made this project possible