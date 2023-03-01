# Api de Games
Projeto criado para representar a criação de uma documentação correta para a API.
Para cada rota criar uma documentação.
## Endpoints
### GET /games
Esse endpoint é responsavel por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parâmetros
Nenhum
#### Respostas
##### 200 - ok
-- Descrição da resposta, caso aconteça vai receber a listagem de todos os games.
Exemplo de resposta:
```
[
    {
        "id": 65,
        "title": "Sea of Thieves Gold Edition",
        "year": "2018",
        "price": "40"
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]
```
##### 401 - Falha na autenticação
Caso essa resposta aconteça isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token Inválidos, Token expirado.

Exemplo de resposta:
```
{
    "err": "Token inválido"
}
```

### POST /auth
Esse endpoint é responsavel por realizar o processo de login.
#### Parâmetros

email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado.

```
{
    "email": "juangranke@outlook.com",
    "password": 123
}
```

#### Respostas
##### 200 - ok
-- Descrição da resposta, caso aconteça vai receber o token JWT para conseguir acessar endpoints protegidos na API.
Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJqdWFuZ3JhbmtlQG91dGxvb2suY29tIiwiaWF0IjoxNjYzNzk0MTI2LCJleHAiOjE2NjM5NjY5MjZ9.cG8NN_iEps5sCaLTvD0opemfrVC8j6e6hlCpGhTXXB4"
}
```
##### 401 - Falha na autenticação
Caso essa resposta aconteça isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail incorretos.

Exemplo de resposta:
```
{
    "err": "Credenciais inválidas"
}
```

