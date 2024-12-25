<h1 align="center">Hi 👋, I'm Daniel Berliant</h1>
<p align="left"> <img src="https://komarev.com/ghpvc/?username=daniel2369&label=Profile%20views&color=0e75b6&style=flat" alt="daniel2369" /> </p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://aws.amazon.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" alt="aws" width="40" height="40"/> </a> <a href="https://www.docker.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="docker" width="40" height="40"/> </a> <a href="https://www.elastic.co" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/elastic/elastic-icon.svg" alt="elasticsearch" width="40" height="40"/> </a> <a href="https://grafana.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/grafana/grafana-icon.svg" alt="grafana" width="40" height="40"/> </a> <a href="https://www.elastic.co/kibana" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/elasticco_kibana/elasticco_kibana-icon.svg" alt="kibana" width="40" height="40"/> </a> <a href="https://www.linux.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="linux" width="40" height="40"/> </a> <a href="https://www.postgresql.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/> </a> <a href="https://postman.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/getpostman/getpostman-icon.svg" alt="postman" width="40" height="40"/> </a> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> </p>

# 🚀 Building a Complete Monitoring Stack with Prometheus, cAdvisor, and Grafana Using Docker Compose – DevOps in Action! 🚀

Monitoring is one of the most important aspects of maintaining modern infrastructure, especially in containerized environments like Docker. In this project, I set up a full observability stack using Prometheus, cAdvisor, and Grafana, all orchestrated with Docker Compose.

## 🌟 Why Monitoring?

With microservices and containers becoming the norm, it’s critical to ensure that our applications are running efficiently and without errors. Proper monitoring helps you:
- Detect performance issues early.
- Ensure system uptime and reliability.
- Optimize resource usage.

## 🔧 Tools Used:

- **[Prometheus](https://prometheus.io/)**: Collects and stores metrics from various services.
- **[cAdvisor](https://github.com/google/cadvisor)**: Provides container-specific performance metrics (CPU, memory, network, etc.).
- **[Grafana](https://grafana.com/)**: Creates beautiful, interactive dashboards for visualizing metrics and system health.

## 🔨 Setup Process:

I automated the entire stack setup using Docker Compose to ensure that this system can be replicated and scaled easily.

### **Setup Steps**

**Note**: You need any container for monitoring for test you can pull Redis, # docker pull redis.
- **Step 1**: Clone this repository
- **Step 2**: Run docker ps -> copy cAdvisor container id -> run: docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container_id> -> save the IP address.
- **Step 2**: Inside prometheus.yml -> paste the IP address inside targets key.
- **Step 3**: Run docker-compose up -d - to start docker, then run docker ps to check if the containers are up.
- **Step 4**: Open in the browser the services:
              1. http://localhost:3000 - Grafana (username&password admin)
              2. http://localhost:9090 - Prometheus
              3. http://localhost:8080 - cAdvisor
- **Step 5**: Inside Prometheus UI -> Status -> Target health - check that the IP and port are correct towards cAdvisor and UP in green.
- **Step 6**: Inside cAdvisor UI -> /dockers -> any containers id that you want to monitor (this is the full id) you can compare with the short id from running docker ps in the terminal. save the entry /docker/full_id
- **Step 7**: Inside Grafana UI -> Connections -> Data sources -> Select Prometheus and under the URL enter: http://host.docker.internal:9090 save & test.
- **Step 8**: Upload the json inside Dashboards.
- **Step 9**: Edit each visulization and replace the container id in the query with the one you copies from step 6. save.

- **Result** Now you have 2 visulizations 1 for CPU and 1 for RAM usage that you can monitor for any container that you run with.
- For more queries check Prometheus DOCS.

## 📊 Key Benefits:

- **Centralized monitoring** of containers running on Docker.
- **Real-time visualization** of system metrics with Grafana dashboards.
- **Simple yet powerful alerting** system for proactive management of system health and resource utilization.

## 💻 LinkedIn Profile

[Connect with me on LinkedIn](https://www.linkedin.com/in/daniel-berliant-6725241a9)

## 💬 Community & Feedback

What monitoring tools are you using in your own DevOps projects? Feel free to share your thoughts or ask questions in the discussions section! Let's connect and learn together.

---

## 🔖 Tags

#DevOps #Monitoring #Prometheus #Grafana #Docker #Containers #cAdvisor #InfrastructureAsCode #Automation #CloudNative
