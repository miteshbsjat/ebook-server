# Dockerized Ebook Server

A lightweight PDF server built with Flask and HTML that provides a simple way to upload, view, search, and serve PDFs. This project was created to meet my personal need for a quick and easy e-book viewing experience.

## **What is it?**

The Docker ebook server offers a no-nonsense way to access your PDF library from any device via a web browser. It's similar to a NAS client app, but with the convenience of browser-based access.

## **What it's not:**

* A comprehensive document organizer like Paperless-ngx
* A database-driven system (it relies on file system organization)
* A folder system (although this feature could be added in the future)
* OAuth authentication (basic HTTP authentication is implemented)

## **Getting Started:**

1. Run the following Docker command, replacing `<your-username>`, `<your-password>`, and `<your-random-secret-key>` with your preferred values:
```
docker run -e DOCKER_PDF_SERVER_USER=<your-username> \
-e DOCKER_PDF_SERVER_PASSWORD=<your-password> \
-e DOCKER_PDF_SERVER_KEY=<your-random-secret-key> \
-p 3040:5000 -v /Users/writable/host/path/pdf-library:/app/library/ miteshbsjat/ebooks-server:latest
```
2. Access the app by going to `http://localhost:3040`

## **Building and Running Locally for Development:**

1. Create a Python venv in this directory: `python -m venv venv` (or `python3 -m venv venv`)
2. Activate the venv: `source venv/bin/activate` (on Linux/macOS) or `env/Scripts/activate.bat` (on Windows)
3. Install dependencies: `pip install -r requirements.txt`
4. Run the app server for development: `python3 app.py` (or `python app.py`)
5. Build a Docker image: `docker build . -t ebooks-server:latest`

## **Ideas and Enhancements:**

I may consider adding features that maintain the server's lightweight nature, such as a folder system. Feel free to contribute or raise issues to improve the Docker ebook server!
