# forumemnodejs
Fórum em Node.JS que permite que o usuário crie ou responda perguntas, que são salvas em um banco de dados.
# Como rodar:
Este é meu primeiro projeto em nodejs, então eu não conhecia muito sobre nodejs, apenas sobre JavaScript.
para rodar o projeto, é necessário ter o NodeJS instalado e rodar```npm install``` para instalar os pacotes utilizados.
Depois use o comando ```node index.js``` para executar o projeto.
É necessário ter um banco de dados MySql rodando na porta 3306 para executar, segue exemplo de docker-compose.yml
```yml
version: "3.3"
services:
  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: "forumnodejs"
      # So you don't have to use root, but you can if you like
      MYSQL_USER: "gustavo"
      # You can use whatever password you like
      MYSQL_PASSWORD: "123456"
      # Password for root access
      MYSQL_ROOT_PASSWORD: "123456"
    ports:
      # <Port exposed> : <MySQL Port running inside container>
      - "3306:3306"
    expose:
      # Opens port 3306 on the container
      - "3306"
      # Where our data will be persisted
    volumes:
      - my-db:/var/lib/mysql
# Names our volume
volumes:
  my-db:

```
Talvez seja necessário editar o arquivo /database/database.js e corrigir os passwords
Após a configuração incial e o projeto rodar, ele será executado na porta 8081, que você pode acessar por um navegador.
```http://localhost:8081```
