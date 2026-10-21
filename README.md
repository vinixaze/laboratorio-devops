# Site estático com Docker e AWS

Meu primeiro projeto DevOps: um site estático servido pelo Nginx em um
container Docker. A imagem foi publicada no Amazon ECR e executada em uma
instância Amazon EC2.

## Tecnologias

- HTML, CSS e JavaScript
- Docker
- Nginx
- Amazon ECR
- Amazon EC2

## Estrutura

```text
.
├── website/
│   ├── css/style.css
│   ├── js/script.js
│   └── index.html
├── .dockerignore
└── Dockerfile
```

## Executar localmente

Crie a imagem:

```bash
docker build -t site-devops .
```

Inicie o container:

```bash
docker run --rm -d -p 8080:80 --name site-devops site-devops
```

Acesse `http://localhost:8080` no navegador.

Para parar o container:

```bash
docker stop site-devops
```

## Fluxo do deploy

```text
Código local -> imagem Docker -> Amazon ECR -> Amazon EC2
```

As credenciais da AWS e a chave privada da EC2 não fazem parte do
repositório.
