#!/bin/bash -e
(
	echo "INFO: Executando o script de instalação!"
	sh build/install.sh
)

# Verifique se podemos pelo menos obter a saída da versão
if ! docker --version; then
	echo "ERROR: O Docker foi instalado?"
	exit 1
fi

# Tentar executar um contêiner se não estiver em um contêiner
if [ ! -f /.dockerenv  ]; then
	if ! docker run --rm hello-world; then
		echo "ERROR: Não foi possível obter o docker para executar o contêiner hello world"
		exit 2
	fi
fi

echo "INFO: Instalação do docker verificada com sucesso!"
