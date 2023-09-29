# Imagem do python
FROM python:3.11-alpine3.17

# Criar pasta no docker
WORKDIR /app

# Copia o arquivo para instação
COPY requirements.txt .

#instala as libs necessarias
RUN pip install -r requirements.txt

# Copia o restantes dos arquivos
COPY . .

# Aloca a porta 8000
EXPOSE 3001

#Inicio o backend
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "3001"]