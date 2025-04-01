# goexpert-leilao
Desafio Fullcycle - Pós GoExpert - Labs - Fechamento de Leilão

## Testar o projeto

1. Baixar e subir os serviços
```

git clone https://github.com/flaviojohansson/goexpert-leilao

cd goexpert-leilao

# Para efeito de aprendizado, este repositório já possui um arquivo .env para rodar o teste

docker compose up -d
```
2. Testar a criação de um leilão
```
curl localhost:8080/auction \
-X POST \
-d '{"product_name": "Esteira ergométrica", "category": "Fitness", "description": "Esteira marca Fatburn.io, suporta 12 Km/h e 100 Kg", "condition": 0}'
```
3. Consultar os leilões criados e abertos
```
curl -X GET localhost:8080/auction?status=0
```
4. Após 10 segundos (definidos na variável AUCTION_INTERVAL do arquivo .env), consultar os leilões criados e finalizados
```
curl -X GET localhost:8080/auction?status=1
```