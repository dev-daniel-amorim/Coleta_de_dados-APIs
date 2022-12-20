# Coleta de dados - API

O que é API?<br>
API é um conjunto de código para usar em um serviço/aplicativo, disponibilizado por aplicações de terceiros para promover integração de forma facilitada com seu código. Essas informações recbidas por APIs geralmente vem em formato JSON, que é uma espécio de dicionário que precisamos tratar para obter as informações desejadas.

# Objetivo
O objetivo deste tutorial é fazer integração com um API de cotação de moedas disponível em:<br>

- <a href="https://docs.awesomeapi.com.br/api-de-moedas"> Abrir site API cotação de moedas</a>

Neste site encontramos informações atualizadas de diversas moedas como REAL, DOLAR e ate mesmo cotação de BITCOINS.<br>
Note que, o site disponibiliza diversos links de consulta JSON, como no exemplo abaixo onde podemos fazer uma requisição e obter a cotação de diversas moedas de diversos países:

        https://economia.awesomeapi.com.br/json/all

# Bibliotecas 
Para iniciar a coleta de dados via API vamos precisar de 2 bibliotecas python:

        import requests
        import json
        
# Coleta de dados

Com o link em mãos vamos realizar o request:

        # fazendo a requisição
        cotacoes = requests.get("https://economia.awesomeapi.com.br/json/all")
        # convertendo json no dicionário
        cotacoes_dict = cotacoes.json()
        # Imprimindo resposta
        print(cotacoes_dict)
        
Obtemos a resposta [200] significa que está ok, imprimindo a solicitação obtemos um dicionário JSON com todas as cotações:

        {'USD': {'code': 'USD', 'codein': 'BRL', 'name': 'Dólar Americano/Real Brasileiro', 'high': '5.3249', 'low': '5.1769', 'varBid': '-0.0883', 'pctChange': '-1.67', 'bid': '5.2039', 'ask': '5.2055', 'timestamp': '1671561034', 'create_date': '2022-12-20 15:30:34'}, 'USDT': {'code': 'USD', 'codein': 'BRLT', 'name': 'Dólar Americano/Real Brasileiro Turismo', 'high': '5.35', 'low': '5.205', 'varBid': '-0.105', 'pctChange': '-1.97', 'bid': '5.07', 'ask': '5.38', 'timestamp': '1671559860', 'create_date': '2022-12-20 15:11:00'}, 'CAD': {'code': 'CAD', 'codein': 'BRL', 'name': 'Dólar Canadense/Real Brasileiro', 'high': '3.9074', 'low': '3.801', 'varBid': '-0.0572', 'pctChange': '-1.47', 'bid': '3.8211', 'ask': '3.8233', 'timestamp': '1671561032', 'create_date': '2022-12-20 15:30:32'}}

Para entender o que significa cada coisa no dicionário, o próprio site nos fornece uma legenda informado o que significa cada coisa:

![Captura de tela 2022-12-20 154706](https://user-images.githubusercontent.com/115194365/208743390-f5e2fdbb-8447-4fdf-9ce5-0a7d259e8334.png)



