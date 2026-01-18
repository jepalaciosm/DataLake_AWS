# 🏗️ Data Lake AWS - Learning Project

> **Un proyecto de aprendizaje integral para dominar la arquitectura moderna de Data Lakes en AWS**

---

## 📋 Descripción del Proyecto

Este es un **proyecto educativo** diseñado para aprender y practicar los principios fundamentales de la construcción de un **Data Lake profesional** utilizando los servicios de **Amazon Web Services (AWS)**. A través de este proyecto, exploraremos las mejores prácticas y patrones arquitectónicos utilizados por Data Engineers en la industria moderna.

### 🎯 Objetivos de Aprendizaje

El proyecto cubre los siguientes aspectos esenciales:

- **Arquitectura de Data Lakes**: Diseño de sistemas escalables y eficientes
- **Ingesta de Datos**: Métodos variados para importar datos desde múltiples fuentes
- **Almacenamiento**: Configuración de S3, Data Lakes structures (Bronze, Silver, Gold)
- **Procesamiento ETL/ELT**: Pipelines con AWS Glue, Lambda y Apache Spark
- **Governanza de Datos**: Metadatos, catálogos y seguridad
- **Análisis y Visualización**: Consultas con Athena y BI tools
- **Monitoreo y Optimización**: CloudWatch, logging y cost optimization

---

## 🚀 Tecnologías y Servicios Utilizados

### AWS Services
- **S3**: Almacenamiento de datos (Data Lake)
- **AWS Glue**: Catálogo de datos y ETL jobs
<!-- - **Lambda**: Procesamiento serverless
- **EC2**: Procesamiento con Spark (opcional)
- **RDS**: Almacenamiento relacional
- **DynamoDB**: Datos NoSQL
- **Athena**: Consultas SQL sin servidor
- **CloudWatch**: Monitoreo y logging
- **IAM**: Seguridad y control de acceso
- **VPC**: Infraestructura de red -->

### Herramientas Adicionales
- **Apache Spark**: Procesamiento distribuido
- **Python**: Lenguaje principal para scripts y pipelines
- **SQL**: Consultas de datos
- **Docker**: Containerización (opcional)
- **Terraform/CloudFormation**: Infrastructure as Code

---

## 📚 Estructura del Proyecto

```
DataLake_AWS/
├── docs/                          # Documentación y guías
│   ├── architecture.md           # Diagrama de arquitectura
│   ├── setup-guide.md            # Guía de configuración
│   └── best-practices.md         # Mejores prácticas
├── infrastructure/               # IaC (Infrastructure as Code)
│   ├── terraform/               # Terraform configs
│   └── cloudformation/          # CloudFormation templates
├── src/                          # Código fuente
│   ├── ingestion/               # Scripts de ingesta
│   ├── processing/              # Jobs ETL/ELT
│   ├── transformation/          # Transformaciones de datos
│   └── utils/                   # Funciones reutilizables
├── tests/                        # Tests unitarios e integración
├── notebooks/                    # Jupyter notebooks para análisis
├── config/                       # Archivos de configuración
│   ├── dev.yaml
│   ├── staging.yaml
│   └── prod.yaml
├── requirements.txt              # Dependencias de Python
├── docker-compose.yml           # Para desarrollo local
├── .env.example                 # Variables de entorno
└── LICENSE                      # Licencia del proyecto
```

---

## ⚡ Características Principales

### 1. **Arquitectura Medallion**
Implementación de la arquitectura de medallón (Bronze → Silver → Gold):
- **Bronze**: Datos crudos sin procesar
- **Silver**: Datos limpios y transformados
- **Gold**: Datos optimizados para análisis

Para esta seccion Usando AWS S3 creamos el siguiente  almacenamiento en S3 (Zonificación)
Un Data Lake sin estructura es un "Data Swamp" (pantano de datos). Crea tres carpetas (o buckets) distintos:

**jpm-raw-zone**: Donde caen los datos crudos (CSV, JSON, logs). 

**jpm-processed-zone**: Datos limpios, con tipos de datos corregidos y en formato Parquet.

**jpm-curated-zone**: Datos listos para el negocio (agregados, joins, etc.).

![Data Lake S3 Architecture](./docs/img/Data%20Lake%20S3.png)

### 2. **Pipelines Automatizados**
- Ingesta automática de datos
- Procesamiento scheduled con Lambda o Glue
- Notificaciones y alertas
- Error handling y retry logic

### 3. **Seguridad y Governanza**
- Encriptación en reposo y en tránsito
- Control de acceso basado en roles (IAM)
- Auditoría de cambios (CloudTrail)
- Política de datos y metadata management

### 4. **Escalabilidad**
- Procesamiento serverless con Lambda
- Spark jobs distribuidos
- Auto-scaling de recursos
- Optimización de costos

---

## 🔧 Requisitos Previos

Antes de comenzar, asegúrate de tener:

- **Cuenta de AWS** (con permisos suficientes o cuenta de desarrollo)
- **AWS CLI** configurado: [Instalar AWS CLI](https://aws.amazon.com/cli/)
- **Python 3.9+**: [Descargar Python](https://www.python.org/)
- **Git**: Para control de versiones
- **Docker** (opcional): Para desarrollo local
- **Terraform** (opcional): Para IaC

### Instalación de Dependencias

```bash
# Clonar el repositorio
git clone <repository-url>
cd DataLake_AWS

# Crear entorno virtual
python -m venv venv

# Activar entorno (Windows)
venv\Scripts\activate

# Activar entorno (macOS/Linux)
source venv/bin/activate

# Instalar dependencias
pip install -r requirements.txt

# Configurar AWS CLI
aws configure
```

---

## 📖 Guía de Inicio Rápido

### 1. Configuración del Entorno
<!-- ```bash
# Copiar archivo de configuración
cp .env.example .env

# Editar con tus valores de AWS
nano .env
``` -->

### 2. Desplegar Infraestructura
<!-- ```bash
# Navegar a infraestructura
cd infrastructure/terraform

# Inicializar Terraform
terraform init

# Planificar cambios
terraform plan

# Aplicar cambios
terraform apply
``` -->

### 3. Ejecutar Primera Ingesta
```bash
cd src/ingestion
python ingest_data.py --source example --environment dev
```

---

## 🎓 Contenidos de Aprendizaje
<!-- 
### Módulo 1: Fundamentos
- [ ] Conceptos de Data Lake
- [ ] Arquitectura AWS para datos
- [ ] Servicio S3 en profundidad
- [ ] IAM y seguridad

### Módulo 2: Ingesta de Datos
- [ ] Patrones de ingesta
- [ ] AWS Glue Crawlers
- [ ] Kinesis y Stream processing
- [ ] Lambda functions

### Módulo 3: Procesamiento
- [ ] Apache Spark en AWS
- [ ] AWS Glue ETL
- [ ] Transformaciones SQL
- [ ] Manejo de errores

### Módulo 4: Análisis
- [ ] Athena y presto
- [ ] Particionamiento de datos
- [ ] Optimización de queries
- [ ] Herramientas BI

### Módulo 5: Producción
- [ ] CI/CD pipelines
- [ ] Monitoreo y alertas
- [ ] Optimización de costos
- [ ] Disaster recovery

---

## 📊 Casos de Uso Cubiertos

- ✅ Ingesta de datos de APIs REST
- ✅ Procesamiento de archivos CSV, Parquet, JSON
- ✅ Stream processing de eventos
- ✅ Transformaciones complejas con Spark
- ✅ Agregaciones y reporting
- ✅ Machine Learning pipelines -->

---

## 🤝 Contribución

Este es un proyecto de aprendizaje abierto. Se aceptan:
- Reportes de bugs
- Mejoras en la documentación
- Nuevos ejemplos y casos de uso
- Sugerencias de mejora

Por favor, crea un **issue** o **pull request** para participar.

---

## 📝 Licencia

Este proyecto está bajo la licencia **MIT** - ver el archivo [LICENSE](LICENSE) para más detalles.

---

## 🔗 Recursos Útiles

### Documentación Oficial
<!-- - [AWS Data Lake Documentation](https://aws.amazon.com/solutions/data-lake/)
- [AWS Glue User Guide](https://docs.aws.amazon.com/glue/)
- [Amazon S3 Best Practices](https://docs.aws.amazon.com/AmazonS3/latest/dev/BestPractices.html)

### Cursos y Tutoriales
- [AWS Certified Data Analytics - Specialty](https://aws.amazon.com/certification/certified-data-analytics-specialty/)
- [Building Data Lakes on AWS](https://aws.amazon.com/training/) -->

### Comunidades
- [AWS Data Engineering Community](https://community.aws/)
- [Stack Overflow - AWS Tag](https://stackoverflow.com/questions/tagged/amazon-web-services)

---

## 👤 Autor

Creado como proyecto de aprendizaje para dominar las competencias de un **Data Engineer moderno** por John Edwar Palacios Moya, en [LinkedIn](www.linkedin.com/in/john-edwar-palacios-748a2692).

**Última actualización**: Enero 2026

---

<div align="center">

**⭐ Si este proyecto te fue útil, considera darle una estrella! ⭐**

*Aprendizaje continuo en Data Engineering*

</div>
