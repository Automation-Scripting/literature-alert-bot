# arXiv → Discord
Este repositório contém um **runner em Python** que busca artigos no **arXiv** (via Atom feed) a partir de um arquivo YAML de tópicos/querys e publica diariamente no **Discord** via **Webhook**.

## 1) Setup
1. Baixe/clone este repositório com todo o código-fonte (inclusive os arquivos da pasta .github/workflows).
2. Suba o código em um **novo repositório** (GitHub) em que você é dono.

<img width="568" height="139" alt="image" src="https://github.com/user-attachments/assets/46935c34-9eec-4524-8109-789223a56d3d" />

## 2) Bind das variáveis
Em cada tópico no arquivo YML, contém a query de busca a ser executada e existe uma variável de ambiente que contém a URL (`webhook`) para onde enviar a mensagem no Discord. Essa variável precisa estar configurada no repositorio do github onde será rodado o runner.

GitHub Repository Settings: criar uma secret com a URL destino do post
<img width="1098" height="130" alt="image" src="https://github.com/user-attachments/assets/0b3b4f4d-30ec-4cd5-97fa-d0102cf11e5d" />
<img width="364" height="150" alt="image" src="https://github.com/user-attachments/assets/87fedf6b-c0b0-4b9d-ae57-f19ea0895da6" />
<img width="941" height="231" alt="image" src="https://github.com/user-attachments/assets/12a48ae3-b40c-4d36-9f12-948a001f2e37" />

Discord: obter a URL do post
<img width="380" height="51" alt="image" src="https://github.com/user-attachments/assets/3215b6d8-578c-4012-a7c7-ff61bf22e1e6" />
<img width="272" height="187" alt="image" src="https://github.com/user-attachments/assets/d5d6e938-0fde-405b-9727-ebed44bc9108" />
<img width="703" height="355" alt="image" src="https://github.com/user-attachments/assets/de0dd352-429c-4bf3-8845-a60d8ea9f87d" />

Tópico (arquivo topico.yml): informar o nome dessa variável
topics/topic.yml: <img width="1190" height="150" alt="image" src="https://github.com/user-attachments/assets/a6425669-3963-4016-8ddf-7e741c9d51ae" />
.github/workflows/check_new_papers.yml: <img width="815" height="320" alt="image" src="https://github.com/user-attachments/assets/2520d651-5ef1-4f25-bba0-2391621221a7" />
  - id: qgp_ml
    title: "QGP + ML"
    webhook_env: DISCORD_WEBHOOK_URL_QGP_ML
    arxiv_url: "https://export.arxiv.org/api/query?...etc..."
