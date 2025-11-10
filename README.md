# DataLake-Playground
Este repositório fornece um ambiente rápido para integração local de Spark, Trino, MinIO, Iceberg e Nessie, com exemplos de queries em Jupyter Notebook. Inclui também uma imagem Dockerizada do DBeaver (CloudBeaver) para visualização e gerenciamento de dados.

## Como executar localmente

1. Clone o repositório e acesse a pasta:
	```bash
	git clone https://github.com/kleidsonfriend/DataLake-Playground.git
	cd DataLake-Playground
	```

2. Crie o diretório de dados local (se ainda não existir):
	```bash
	mkdir -p data
	```

3. Suba todos os serviços (incluindo 3 workers do Trino):
	```bash
	docker compose up --scale trino-worker=3 -d
	```

4. Verifique se todos os serviços estão rodando:
	```bash
	docker compose ps
	```

## Serviços e portas

| Serviço        | URL/Porta                      | Usuário/Senha         |
|---------------|---------------------------------|-----------------------|
| Jupyter       | http://localhost:8888           | Token: TestTest123    |
| Trino         | http://localhost:8080           | -                     |
| MinIO Console | http://localhost:9001           | admin / password      |
| CloudBeaver   | http://localhost:8089           | TestTest123 / TestTest123 |
| Nessie        | http://localhost:19120          | -                     |
| PostgreSQL    | localhost:5432                  | postgres / postgres   |

Os dados são persistidos localmente na pasta `./data`.

## Observações
- Não é necessário nenhuma credencial AWS para rodar localmente.
- Os notebooks de exemplo estão em `jupyter/notebooks/`.
- Para acessar o Jupyter, use o token informado acima.

---
Ambiente testado em Docker Compose e Ubuntu 20.04+.