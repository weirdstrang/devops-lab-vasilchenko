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
# Подготовка проекта
**Копирование файлов из lab1 в новый репозиторий:** https://github.com/weirdstrang/lab2-devops-vasilchenko
<img width="1914" height="873" alt="image" src="https://github.com/user-attachments/assets/304c8f79-c50c-4859-b995-0a6a5ac21c24" />

**Создать аккаунт на Docker Hub. Создать новый репозиторий на Docker Hub для вашего образа:** https://hub.docker.com/r/weirdstrang/lab2-devops-vasilchenko 
<img width="1905" height="835" alt="image" src="https://github.com/user-attachments/assets/52df8d7e-4eb2-4f23-a392-c2cc19b8be82" />


# Настройка GitHub Actions
name: Build and Push Docker Image

on:
  push:
    branches: [ main ]

jobs:
  build-and-push:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v4
    
    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v3
    
    - name: Login to Docker Hub
      uses: docker/login-action@v3
      with:
        username: ${{ secrets.DOCKERHUB_USERNAME }}
        password: ${{ secrets.DOCKERHUB_TOKEN }}
    
    - name: Build and push Docker image
      uses: docker/build-push-action@v5
      with:
        context: .
        push: true
        tags: ${{ secrets.DOCKERHUB_USERNAME }}/my-flask-app:latest
    
    - name: Deploy application
      run: |
        echo "🚀 Starting deployment process..."
        echo "✅ Docker image ${{ secrets.DOCKERHUB_USERNAME }}/my-flask-app:latest successfully built and pushed"
        echo "📦 Image is ready for deployment"
        echo "🎯 Deployment simulation completed successfully!"

# Настройка секретов:
<img width="1911" height="913" alt="image" src="https://github.com/user-attachments/assets/34860807-5565-4ecc-b577-b68bbdd5fa84" />

#Тестирование пайплайна
**Сделать коммит и пуш в main ветку**
<img width="1903" height="750" alt="image" src="https://github.com/user-attachments/assets/ad9dc3b8-0e4b-4d70-a212-44d082209af9" />
**Проверить выполнение пайплайна в разделе Actions**
<img width="730" height="298" alt="image" src="https://github.com/user-attachments/assets/0b0846e5-4a8b-423c-a455-93ae31fec857" />
**Убедиться, что образ появился в Docker Hub**
<img width="633" height="717" alt="image" src="https://github.com/user-attachments/assets/a06cb8fb-612e-4e50-b872-2f7cfcc29184" />
**Проверить логи выполнения каждого шага**
<img width="1587" height="783" alt="image" src="https://github.com/user-attachments/assets/2c657620-8f6d-4696-ac42-6ceecc19e66f" />
<img width="1520" height="317" alt="image" src="https://github.com/user-attachments/assets/c2d2fbe5-b68b-423f-8244-0efa646387b5" />
<img width="1522" height="839" alt="image" src="https://github.com/user-attachments/assets/9a40cc39-9071-4ffb-8c8a-5212b9caf460" />
<img width="1468" height="812" alt="image" src="https://github.com/user-attachments/assets/bb786edb-1494-4243-89f9-d521f8a006d2" />
<img width="1487" height="808" alt="image" src="https://github.com/user-attachments/assets/6848b3e9-d034-492e-9f32-7223454fd2d3" />
<img width="1492" height="808" alt="image" src="https://github.com/user-attachments/assets/5a7d20f9-ef90-4510-959d-235f99f2c50f" />
<img width="1486" height="804" alt="image" src="https://github.com/user-attachments/assets/8c486532-34a2-4454-acd8-a18d54695033" />
<img width="1466" height="808" alt="image" src="https://github.com/user-attachments/assets/d5d008fa-3608-49cc-ae8b-5cd27fb999c1" />
<img width="1363" height="807" alt="image" src="https://github.com/user-attachments/assets/0ac53954-9b65-4a13-99d8-7abd2f5620d5" />
<img width="1328" height="804" alt="image" src="https://github.com/user-attachments/assets/96acee17-8834-42c8-ae56-086775897fd4" />
<img width="1486" height="805" alt="image" src="https://github.com/user-attachments/assets/d59c0f62-1025-4c0c-957e-383aa8d7c12d" />
<img width="998" height="286" alt="image" src="https://github.com/user-attachments/assets/1457556c-53b4-4011-b191-06a1327d636e" />




















