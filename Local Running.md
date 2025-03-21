# Running Demo Locally

## Running Codellama in Ollama Locally

### Prerequisites
1. **Install Ollama**: Download and install Ollama from [Ollama's official website](https://ollama.ai/).
2. **System Requirements**:
   - A machine with sufficient CPU/GPU resources for running Codellama.
   - Ensure you have at least 16GB of RAM for optimal performance.
3. **Codellama Model**: Ensure the Codellama model is available in your Ollama setup.

### Steps to Run Codellama Locally
1. **Start Ollama**:
   - Open a terminal and start the Ollama service:
     ```bash
     ollama start
     ```

2. **Download Codellama Model**:
   - Use the following command to download the Codellama model:
     ```bash
     ollama pull codellama
     ```

3. **Run Codellama**:
   - Start interacting with the Codellama model:
     ```bash
     ollama run codellama
     ```
## Running laravel-crm locally
### Prerequisites
1. **Install PHP**: Ensure you have PHP installed on your machine. You can download it from [PHP's official website](https://www.php.net/).
2. **Install Composer**: Download and install Composer from [Composer's official website](https://getcomposer.org/).
3. **Add Loki variables in .env**: Add the following variables to your `.env` file: They can be found in the Teams group chat.
   ```env
   LOKI_URL=https://logs-prod-012.grafana.net
   LOKI_USERNAME=your_username
   LOKI_PASSWORD=your_password
   ```

### Steps
1. **Clone the Repository**: Clone the laravel-crm repository to your local machine:
   ```bash
   git clone https://github.com/octoobservo/laravel-crm
   cd laravel-crm
   ```
2. Follow the readme file to install the dependencies and run the application. I uncommented some php.ini settings to get it to run. Please check the php.ini for reference.

## Running RAG
### Prerequisites
1. **Install Python**: Ensure you have Python installed on your machine. You can download it from [Python's official website](https://www.python.org/).

We are going to RAG a dependency that is used by laravel-crm. https://github.com/octoobservo/monolog-loki. It has a few files that we can use to test the RAG functionality considering the limited resource on a laptop.

### Steps
1. **Clone the Repository**: Clone the monolog-loki repository to your local machine:
   ```bash
   git clone https://github.com/octoobservo/monolog-loki
   cd monolog-loki
   ```

2. **Clone the RAG Repository**:
   ```bash
   git clone https://github.com/octoobservo/windbag
   ```

3. **Test on Windows**:
    ```bash
    cd windbag
    python -m venv venv
    venv\Scripts\activate
    pip install -r requirements.txt
    ```
    Change the `test_php_repo_path` variable in `test_chat_code.py` to the path of the monolog-loki repository on your local machine.

    ```bash
    python test_chat_code.py
    ```

    The first time you run this, it will take a while to perform the RAG on the repository by calling `code.ingest(test_php_repo_path)`. After that, we can use `code.load()` to avoid the overhead of re-running the RAG.