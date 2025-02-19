# My Streamlit App on Docker 🚀

This project is a Streamlit application containerized with Docker, deployed on an Amazon Linux EC2 instance. It showcases a data-driven web app using `mushroom.csv` as the dataset.

---

## 📂 **Project Structure**

```plaintext
.
├── Dockerfile
├── app.py
├── requirements.txt
└── mushroom.csv
```

- **Dockerfile**: Defines the container image.
- **app.py**: Main Streamlit application script.
- **requirements.txt**: Python dependencies.
- **mushroom.csv**: Dataset used in the app.

---

## 🚀 **Features**

- Interactive UI built with Streamlit.
- Dockerized for consistent deployment.
- Deployed on Amazon Linux EC2.

---

## ⚙️ **Setup and Installation**

1. **Clone the Repository**
```bash
git clone https://github.com/mitul-2210/your-repo-name.git
cd your-repo-name
```

2. **Build Docker Image**
```bash
docker build -t my_app:V1 .
```

3. **Run the Docker Container**
```bash
docker run -d -p 8501:8501 my_app:V1
```

4. **Access the App**  
Open your browser and go to: `http://<EC2-IP>:8501`

---

## 📝 **Configuration Notes**

- Ensure port `8501` is open in your EC2 Security Group.
- If the port is in use, try a different port:
```bash
docker run -d -p 8601:8501 my_app:V1
```

---

## 📦 **Dependencies**

- **Streamlit**: Interactive web app framework.
- **Pandas**: Data manipulation and analysis.

All dependencies are listed in `requirements.txt`.

---

## 🐳 **Docker Notes**

- To list running containers:
```bash
docker ps
```
- To stop a container:
```bash
docker stop <container_id>
```
- To remove a container:
```bash
docker rm <container_id>
```

---

## 📊 **Dataset**

`mushroom.csv` is used for data visualization in the app.

---

## 🌐 **Deployment on EC2**

1. Transfer files to EC2 using SCP:
```bash
scp -i "docker.pem" Dockerfile app.py requirements.txt mushroom.csv ec2-user@<EC2-IP>:~/
```

2. Connect to EC2:
```bash
ssh -i "docker.pem" ec2-user@<EC2-IP>
```

3. Build and Run Docker on EC2:
```bash
docker build -t my_app:V1 .
docker run -d -p 8501:8501 my_app:V1
```

---

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🤝 **Contributing**

1. Fork the repo.
2. Create a new branch (`feature/new-feature`).
3. Commit your changes.
4. Push to the branch.
5. Open a Pull Request.

---

## ✨ **Acknowledgments**

- Streamlit Community
- Docker Documentation
- Amazon Web Services

---

## 🔗 **Connect with Me**

- GitHub: [mitul-2210](https://github.com/mitul-2210)
- LinkedIn: [Your LinkedIn Profile](#)

---

Happy Coding! 🎉
