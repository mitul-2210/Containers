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

1. Create an EC2 instance on AWS , add a rule to it for port 8501:
![image](https://github.com/user-attachments/assets/976718f2-984c-463b-869a-0dbe600852e2)


2. Connect to EC2(using ec2 connect on AWS):
![image](https://github.com/user-attachments/assets/8dcd5fcc-5f2c-454b-a6a6-7b0504fa5030)
![image](https://github.com/user-attachments/assets/c3972d94-cce4-4e6e-9fb6-2a348f6b0d8d)

3. Transfer files to EC2 using SCP:
```bash
scp -i "docker.pem" Dockerfile app.py requirements.txt mushroom.csv ec2-user@<EC2-IP>:~/
```
![image](https://github.com/user-attachments/assets/95720fa4-11f3-48fc-9c5b-8f218dc545bf)

4. Install docker on the EC2 instance:
'''bash
sudo yum update -y
sudo yum install docker -y
'''
![image](https://github.com/user-attachments/assets/368b7962-2da6-4c42-846f-536f834a852e)

4. Build and Run Docker on EC2:
```bash
docker build -t my_app:V1 .
docker run -d -p 8501:8501 my_app:V1
```
![image](https://github.com/user-attachments/assets/230e1f25-6798-4138-89e1-d134f4bf0d9a)
![image](https://github.com/user-attachments/assets/4927b096-5e10-479d-b2bf-948fd7ab24b7)

5. Go to the public ip of your EC2
-> http://your-instance-public-ip:8501/
   ![image](https://github.com/user-attachments/assets/0003f575-2d16-4420-b14e-7afd3347e70b)


---

