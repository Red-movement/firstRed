#traigo la distro de linux, esta es livianita y por eso me gusto
FROM alpine:3.18

#instalo python pip
RUN apk add --no-cache python3-dev
RUN apk add --no-cache py3-pip
RUN pip3 install --upgrade pip

#indico mi directorio de trabajo
WORKDIR /app

# copio todo a ese directorio
COPY . /app

#instalo dependencias
RUN pip3 --no-cache install -r requirements.txt

#ejecuto mi server
CMD ["python3", "src/app.py"]