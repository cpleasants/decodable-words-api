# Decodable Words API

## Overview

`decodable-words-api` is a simple Python API that takes a set of phonetic criteria and generates a list of words that match those criteria. It utilizes the `decodable_words_generator` library to access a dictionary of words and their features.

## Features

- **Word Filtering:** The API allows users to filter words based on hard consonants, soft consonants, and short vowels.
- **CORS Support:** The API supports Cross-Origin Resource Sharing (CORS) to enable interaction with local frontend applications.

## Installation

To install the necessary dependencies, you can use pip with the provided pyproject.toml file:

```bash
pip install -e .
```

This will install the following dependencies:

- `fastapi`
- `pydantic`
- `pandas`
- `joblib`
- `numpy`
- `decodable_words_generator`

## Usage

1. **Run the API**: To start the FastAPI server, run the following command:

    ```bash
    uvicorn decodable_words_api.api:app --reload
    ```

    The API will be accessible at `http://localhost:8000`.

2. **API Endpoints**:

    - **`POST /filter_words_api`:**
        - **Request Body:**
    ```json
    {
    "hard_consonants": ["t", "k"],
    "soft_consonants": ["s", "j"],
    "short_vowels": ["a", "e"]
    }
    ```
- Response: A list of filtered words based on the provided criteria.

### Bad Words Filter
The API includes a set of inappropriate words that are filtered out from user input. This is to ensure that the generated list of words is appropriate for all audiences.

### License
This project is licensed under the AGPL-3.0-or-later License.

### Author
Chris Pleasants (chris.j.pleasants@gmail.com)