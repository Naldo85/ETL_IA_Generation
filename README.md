# ETL_IA_Generation

Original file is located at
    https://colab.research.google.com/drive/1WzC9c7fuUEU2yAxFPjvUb-6Zns-S3ALg

# Santander Dev Week 2023 (ETL com Python)

**Contexto:** Você é um cientista de dados no Santander e recebeu a tarefa de envolver seus clientes de maneira mais personalizada. Seu objetivo é usar o poder da IA Generativa para criar mensagens de marketing personalizadas que serão entregues a cada cliente.

**Condições do Problema:**

1. Você recebeu uma planilha simples, em formato CSV ('SDW__2023.csv'), com uma lista de IDs de usuário do banco:
  ```
  UserID
  1
  2
  3
  4
  5
  ```
2. Seu trabalho é consumir o endpoint `GET https://sdw-2023-prd.up.railway.app/users/{id}` (API da Santander Dev Week 2023) para obter os dados de cada cliente.
3. Depois de obter os dados dos clientes, você vai usar a API do ChatGPT (OpenAI) para gerar uma mensagem de marketing personalizada para cada cliente. Essa mensagem deve enfatizar a importância dos investimentos.
4. Uma vez que a mensagem para cada cliente esteja pronta, você vai enviar essas informações de volta para a API, atualizando a lista de "news" de cada usuário usando o endpoint `PUT https://sdw-2023-prd.up.railway.app/users/{id}`.

## **E**xtract

Extraia a lista de IDs de usuário a partir do arquivo CSV. Para cada ID, faça uma requisição GET para obter os dados do usuário correspondente.


## **T**ransform

#### Utilize a API do OpenAI GPT-4 para gerar uma mensagem de marketing personalizada para cada usuário.

* Documentação Oficial da API OpenAI: https://platform.openai.com/docs/api-reference/introduction

* Informações sobre o Período Gratuito: https://help.openai.com/en/articles/4936830

#### Para gerar uma API Key:
  1. Crie uma conta na OpenAI
  2. Acesse a seção "API Keys"
  3. Clique em "Create API Key"

 * Link direto: https://platform.openai.com/account/api-keys

## **L**oad

##### Atualize a lista de "news" de cada usuário na API com a nova mensagem gerada.

