# San Antonio 311 Calls Pipeline

A full end-to-end data pipeline for ingesting and processing data from the San Antonio 311 Calls database.

## Overview

This project implements a robust, production-ready data pipeline designed to ingest 311 service request data from San Antonio. The pipeline is built with modern data engineering best practices to ensure reliability, efficiency, and data quality.

## Features

- **Idempotency**: Safely handle retries without duplicating data
- **Batch and Incremental Ingestion**: Flexible data loading strategies to optimize performance and resource usage
- **Watermarking**: Track data ingestion progress with timestamp-based watermarks
- **Metadata Management**: Comprehensive tracking of pipeline execution, data lineage, and quality metrics

## Project Structure

```
San-Antonio-311-Calls-Pipeline/
├── README.md
├── src/
├── config/
├── tests/
└── docs/
```

## Getting Started

### Prerequisites

- Python 3.8+
- Required dependencies (see `requirements.txt`)

### Installation

```bash
git clone https://github.com/ajramos31/San-Antonio-311-Calls-Pipeline.git
cd San-Antonio-311-Calls-Pipeline
pip install -r requirements.txt
```

### Configuration

Configuration files can be found in the `config/` directory. Update these with your San Antonio 311 API credentials and database connection details.

## Data Pipeline Architecture

The pipeline follows these main stages:

1. **Extract**: Pull data from the San Antonio 311 Calls database
2. **Transform**: Process and clean the data
3. **Load**: Store processed data in the target data warehouse

## Key Components

### Idempotency
Ensures that re-running the pipeline produces the same results without creating duplicate records.

### Watermarking
Uses timestamp watermarks to track which data has been processed, enabling efficient incremental ingestion.

### Batch Processing
Configurable batch sizes for processing large volumes of 311 call data efficiently.

### Metadata Management
Automatically captures and stores metadata including:
- Ingestion timestamps
- Record counts
- Data quality metrics
- Pipeline execution logs

## Usage

```bash
python run_pipeline.py --mode incremental --batch-size 1000
```

## Testing

Run the test suite with:

```bash
pytest tests/
```

## Contributing

Contributions are welcome! Please submit pull requests with clear descriptions of changes.

## License

This project is licensed under the MIT License - see LICENSE file for details.

## Contact

For questions or issues, please reach out to [ajramos31](https://github.com/ajramos31).

## Acknowledgments

- San Antonio 311 Calls Database
- Data engineering best practices community
