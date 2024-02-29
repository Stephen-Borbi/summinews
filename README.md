
# Summinews(Final portofolio Project Alx)

# Website Summary App with ChatGPT, Streamlit, Python, and Docker

## Overview
This project aims to create a web application that summarizes news articles using ChatGPT and presents them through Streamlit. We'll also containerize the application using Docker for easy deployment.

## Prerequisites
Make sure you have the following installed:
- **Docker**: If not installed, follow the instructions on the [Docker website](https://docs.docker.com/get-docker/).
- **Python**: Ensure you have Python installed (preferably Python 3.6 or later).

## Getting Started
1. **Clone the Repository**:
   ```
   git clone <your-repo-url>
   cd <your-repo-directory>
   ```

2. **Create a Virtual Environment** (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate
   ```

3. **Install Dependencies**:
   ```
   pip install -r requirements.txt
   ```

4. **Run the Application Locally**:
   ```
   streamlit run app.py
   ```

5. **Access the Web App**:
   Open your browser and navigate to `http://localhost:8501`.

## Dockerization
We'll use Docker to containerize our application. Follow these steps:

1. **Create a Dockerfile**:
   Create a file named `Dockerfile` in your project directory with the following content:
   ```Dockerfile
   FROM python:3.8

   WORKDIR /app

   COPY requirements.txt requirements.txt
   RUN pip install -r requirements.txt

   COPY . .

   CMD ["streamlit", "run", "app.py"]
   ```

2. **Build the Docker Image**:
   ```
   docker build -t website-summary-app .
   ```

3. **Run the Docker Container**:
   ```
   docker run -p 8501:8501 website-summary-app
   ```

4. **Access the Web App**:
   Open your browser and navigate to `http://localhost:8501`.

## Contributing
Feel free to contribute by opening issues or pull requests. Let's make this app even better together!

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---


# Other

This application summarizes daily news from TV News Archive of the Internet Archive using GPT.

To run it locally (in Docker), clone this repository and build a docker image:

```
$ docker image build -t newsum .
```

Run a container from the freshly built Docker image using an OpenAI API key:

```
$ docker container run --rm -it -p 8501:8501 -e OPENAI_API_KEY="<APIKEY>" newsum
```

Access http://localhost:8501/ in a web browser for interactive insights.
