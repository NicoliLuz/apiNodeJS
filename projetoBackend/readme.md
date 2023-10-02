*Passo 1: Iniciação...*

Criar a pasta do projeto
```
mkdir "nome do projeto"
```

Acessar o projeto
```
cd "nome do projeto"
```

Criar arquivo para documentar
```
touch readme.md
```

Iniciar o gerenciador de pacotes do node
```
npm init -y
```

Instalar os pacotes
```
npm i express nodemon dotenv
```

Abrir no VSCode
```
code .
```

Cria o arquivo .gitignore 
```
nano .gitignore
```

Adicionar no .gitignore o nome da pasta
```
node_modules
```

Criar arquivos na pasta src
```
touch src/app.js
```

Arquivo responsável por criar a configuração da api
```
touch src/server.js
```

Arquivo que recebe as configurações e roda a api
```
mkdir src/config
```

Pasta que gerencia a conexão com o banco de dados
```
mkdir src/controllers
```

Pasta que gerencia as requisições das rotas e a conexão com banco de dados
```
mkdir src/routes
```

*Passo 2: Após o git clone...*


Criar o arquivo .env na raiz do projeto para armazenar as variáveis que serão reutilizadas na aplicação
```
nano .env
```

Digitar no .env, essa variavel contém a porta que o servidor está rodando
```
PORT = 3008
```

Adicionamos o .env no .gitignore
```
nano .gitignore
.env
```

Criar arquivo de exemplo para as variaveis necessárias da aplicação
```
nano .env.example
```

Adicionar ao arquivo .env.example
```
PORT = 
```

Importar os pacotes do express (servidor) no arquivo app.js
```
const express = require('express');
```

Importar o pacote dotenv, gerenciador de variavies no app.js
```
const dotenv = require('dotenv').config();
```

Instalar o express na variavel app
```
const app = express();
```

Setar a porta do servidor a partir do .env
```
app.set('port', process.env.PORT || 3333);
```

Exportar as configurações na variavel app
```
module.exports = app;
```

Importar o arquivo app no server.js
```
const app = require('./app');
```

Importar a porta do servidor no server.js
```
const port = app.get('port');
```

Testar API com a função listen (no server.js)
```
app.listen(port, () => {
    console.log(`Running on port ${ port }!`);
});
```

Abrir o package.json para executar, substituir o comando test
```
"start":"nodemon src/server.js"
```

Rodar o comando no terminal com Git Bash
```
npm run start
```