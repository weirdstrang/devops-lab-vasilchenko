University: ITMO University  
Faculty: FTMI  
Course: Введение в веб технологии  
Year: 2025/2026  
Group: U4225  
Author: Vasilchenko Irina Sergeevna  
Lab: Lab1* 
Date of create: 10.10.2025 
Date of finished: 13.10.2025 
***

**Создание файлов проекта: app.py и requirements.txt. Создание Dockerfile** – отдельные файлы в папке  
# Проверка работы
<img width="935" height="884" alt="image" src="https://github.com/user-attachments/assets/aaa214da-5c13-472f-8b62-1b41d282fb6e" />

Microsoft Windows [Version 10.0.19045.6332]  
(c) Корпорация Майкрософт (Microsoft Corporation). Все права защищены.  

C:\Users\Ирина>cd Desktop  

C:\Users\Ирина\Desktop>  
C:\Users\Ирина\Desktop>cd ICT-Minor  

C:\Users\Ирина\Desktop\ICT-Minor>docker build -t my-flask-app:v1 .  
[+] Building 11.1s (12/12) FINISHED                                                docker:desktop-linux  
 => [internal] load build definition from Dockerfile                                               0.0s  
 => => transferring dockerfile: 362B                                                               0.0s  
 => [internal] load metadata for docker.io/library/python:3.9-slim                                 0.3s  
 => [internal] load .dockerignore                                                                  0.0s  
 => => transferring context: 2B                                                                    0.0s  
 => [1/7] FROM docker.io/library/python:3.9-slim@sha256:151b796af055298f244bc4d203bc19e19b0e63c8a  0.0s  
 => => resolve docker.io/library/python:3.9-slim@sha256:151b796af055298f244bc4d203bc19e19b0e63c8a  0.0s  
 => [internal] load build context                                                                  0.0s  
 => => transferring context: 102B                                                                  0.0s  
 => CACHED [2/7] WORKDIR /app                                                                      0.0s  
 => CACHED [3/7] RUN apt-get update && apt-get install -y curl vim && rm -rf /var/lib/apt/lists/*  0.0s  
 => [4/7] COPY requirements.txt .                                                                  0.0s  
 => [5/7] RUN pip install --no-cache-dir -r requirements.txt                                       8.5s  
 => [6/7] COPY app.py .                                                                            0.1s  
 => [7/7] RUN useradd -u 1000 -m appuser                                                           0.5s  
 => exporting to image                                                                             1.5s  
 => => exporting layers                                                                            0.8s  
 => => exporting manifest sha256:9ea1c8d7a81925eaa3951852389a23101eeec77e02bad2f9552abc66d96ed739  0.0s  
 => => exporting config sha256:96043cff013e164a4bd1172b477ecd864c9789ffcf05c2aecb1d93314d832621    0.0s  
 => => exporting attestation manifest sha256:cf72ebd201d99b4696c7ff844bc9187828e7c188e0cf699d2cd3  0.0s  
 => => exporting manifest list sha256:63f4fb38387149fced9b49376d78b24ed526ea80f4b58e43c8483ef6a16  0.0s  
 => => naming to docker.io/library/my-flask-app:v1                                                 0.0s  
 => => unpacking to docker.io/library/my-flask-app:v1                                              0.4s  

C:\Users\Ирина\Desktop\ICT-Minor>docker run -d -p 5000:5000 --name flask-container my-flask-app:v1  
3ede4807156795799783f9a3f25e35123ac73a362434bc3df6b38a34e7b38391  

C:\Users\Ирина\Desktop\ICT-Minor>curl http://localhost:5000  
Hello from Docker!  

C:\Users\Ирина\Desktop\ICT-Minor>
