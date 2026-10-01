# Prova_computa-o_nuvem
Prova 1

# Nginx com Docker

## Objetivo

Criar uma página HTML e hospedá-la usando Nginx em um container Docker.

## Comandos

Criar o arquivo HTML:

```bash
cat > index.html <<'EOF'
<!DOCTYPE html>
<html lang="pt-BR">
<head>
 <meta charset="UTF-8">
 <title>Reservas</title>
</head>
<body>
 <h1>Reservas abertas</h1>
</body>
</html>
EOF
```

Criar o container:

```bash
docker run -d --name reservas -p 8086:80 nginx:alpine
```

Copiar o HTML para o container:

```bash
docker cp index.html reservas:/usr/share/nginx/html/index.html
```

Verificar:

```bash
docker ps
```

Testar:

```bash
curl http://localhost:8086
```

## Resultado

O Nginx foi executado com sucesso no Docker e a página **"Reservas abertas"** foi acessada pela porta **8086**.
