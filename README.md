# 📄 Documentação: Coleta de Dados via API NASA

## 1. Descrição da Atividade
Este projeto consiste em desenvolver um script em Python para coletar dados de um rover da NASA (Perseverance) utilizando a [API da NASA](https://api.nasa.gov/). O script automatiza a coleta de imagens registradas pelo rover em múltiplas datas, organiza os resultados em pastas nomeadas com a data da captura e salva os dados em arquivos CSV.

---

## 2. Processo de Desenvolvimento

- **Tecnologias utilizadas**:
  - Linguagem: Python
  - Bibliotecas: `requests`, `pandas`, `os`, `datetime`

- **Funcionalidades principais**:
  - A função `obter_dados_api()` realiza a solicitação dos dados via HTTP GET e retorna o JSON com os resultados.
  - A função `processar_dia(data)` formata a data para o padrão da API, realiza a coleta dos dados e organiza os resultados em diretórios por data.
  - Os dados são armazenados no diretório `nasa/`, criado automaticamente se não existir.

---

## 3. Evidências de Execução

- A execução do script gerou diretórios com nomes no formato `YYYY-MM-DD`, contendo arquivos CSV com os metadados das fotos.
- Imagens foram coletadas e salvas conforme a resposta da API.
- Prints e amostras de CSV foram gerados (incluir aqui evidências: prints das pastas e do CSV, se desejar).

---

## 4. Organização dos Dados

Os dados são organizados da seguinte forma:

```
nasa/
├── 2021-06-01/
│   ├── dados.csv
│   ├── img_1.jpg
│   ├── img_2.jpg
│   └── ...
├── 2021-06-02/
│   └── ...
```

Cada pasta representa uma data e contém:
- Um arquivo `dados.csv` com metadados das fotos (câmera, rover, ID da imagem, etc).
- As imagens JPEG coletadas via URL.

---

## 5. Coleta de Fotos

As imagens foram coletadas utilizando os links de imagem retornados pela API. Apenas imagens disponíveis foram baixadas (menos de 3 dias utilizados como exemplo, conforme orientação).

---

## 6. Considerações Finais

- O script está preparado para ser evoluído com parâmetros como: rover, câmera, intervalo de datas e limite de fotos por dia.
- Futuras melhorias podem incluir:
  - Interface de linha de comando.
  - Verificação de duplicatas.
  - Armazenamento em banco de dados para consultas futuras.
