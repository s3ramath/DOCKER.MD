# DOCKER.MD

# 🧠 Docker Containerization Planning Checklist

This document helps you ask the right questions before starting to containerize an application using Docker.  
Use it as a planning tool before writing any Dockerfile or Compose configuration.

---

## 🔍 1. What type of application is it?
- [ ] Is it a web app, API, worker, or CLI tool?
- [ ] What language/framework is it using (Node.js, Python, .NET, etc.)?

## 📂 2. How is the app structured?
- [ ] What is the entry point? (`app.py`, `main.js`, etc.)
- [ ] Where are the dependencies listed? (`requirements.txt`, `package.json`, etc.)

## 📦 3. What are the dependencies?
- [ ] Does it need a database? (e.g., PostgreSQL, MongoDB)
- [ ] Does it require a cache or message queue? (e.g., Redis, RabbitMQ)
- [ ] Are other services needed?

## ⚙️ 4. How do you run the app locally?
- [ ] Command to run the app (e.g., `python app.py`, `npm start`)
- [ ] Does it require a build step? (`npm run build`, `dotnet publish`, etc.)

## 📤 5. What ports does the app use?
- [ ] What port does the app listen on?
- [ ] Is the port configurable via environment variables?

## 📁 6. Which files should be included in the image?
- [ ] What files need to be copied?
- [ ] What files should be excluded using `.dockerignore`?

## 🔐 7. What environment variables are needed?
- [ ] DB credentials
- [ ] API keys
- [ ] Secret keys or tokens

## 📦 8. Do we need persistent data or volumes?
- [ ] Does the app read/write local files or logs?
- [ ] Should a Docker volume be used?

## 📄 9. What should the Dockerfile do?
- [ ] Which base image is appropriate?
- [ ] Are OS packages needed (`curl`, `gcc`, etc.)?
- [ ] What is the `CMD` or `ENTRYPOINT`?
- [ ] Should a multi-stage build be used?

## 🚀 10. How will you test the container?
- [ ] What logs or endpoints confirm the app is working?
- [ ] How do you know the container is healthy?

---

## 🧰 Compose-specific Questions (for multi-service setups)

- [ ] What services are needed?
- [ ] How should they connect (internal network, links)?
- [ ] What environment variables should be passed between services?
- [ ] What ports should be exposed?
- [ ] Should volumes or secrets be shared?

---

> ✅ Fill this out before containerizing any app — it helps prevent mistakes and makes your container setup production-ready.

