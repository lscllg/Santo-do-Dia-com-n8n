# 🕊️ Santo do Dia — Automação com n8n

Todo dia às 6h da manhã, chega no meu e-mail o santo do dia com uma frase ou oração dele.
Foi meu primeiro projeto no n8n: simples, mas funciona todo dia e me ensinou o básico de automação.

![Uploading image.png…]()

## Como funciona

O workflow tem só 3 nós:

1. **Schedule Trigger**: dispara todo dia às 6h (fuso America/Sao_Paulo).
2. **Google Sheets**: lê uma planilha com um santo por dia do ano e filtra a linha cuja coluna `data` é igual à data de hoje (formato `dd/MM`).
3. **Gmail**: manda um e-mail com o nome do santo e a frase/oração.

![Uploading image.png…]()

## Estrutura da planilha

| data  | santo             | frase                        |
|-------|-------------------|------------------------------|
| 13/11 | São Diogo de Alcalá | São Diogo de Alcalá, rogai por nós. |


## Tecnologias

n8n · Google Sheets · Gmail

## Como reproduzir

1. Crie uma conta no [n8n](https://n8n.io) (ou rode localmente).
2. Importe o arquivo `workflow/santo-do-dia.json` (menu ⋯ → *Import from file*).
3. Monte sua planilha seguindo a estrutura acima.
4. Conecte suas credenciais do Google (Sheets e Gmail) nos nós.
5. Aponte o nó do Sheets pra sua planilha e troque o e-mail de destino no nó do Gmail.
6. Publique o workflow.

## Aprendizados

- Primeiro contato com automação por gatilho de horário
- Uso de expressões do n8n (`$now.toFormat('dd/MM')`) pra filtrar pela data
- Conectar serviços do Google via OAuth
- Cuidado com fuso horário e formato de data na planilha
