# Fine tuning BERT - AI vs Human Text

Apresentação Final do grupo de estudos de Processamento em Linguagem Natural no Panda (UFSCar)

**Membros:**

    Leticia Bossatto Marchezi
    
    Leonardo Rossi
    
    Lorhanne Martins

**Introdução**  
Neste tutorial, faremos o fine tuning de um modelo transformer para o problema de classificação de texto binária. Este é um dos problemas de negócios mais comuns, onde um dado texto/frase/documento precisa ser classificado em uma ou mais categorias de uma lista fornecida. Por exemplo, um filme pode ser categorizado em um ou mais gêneros.

**Fluxo do Notebook**  
O notebook será dividido em seções separadas para fornecer um guia organizado sobre o processo utilizado. Este processo pode ser modificado para casos de uso individuais. As seções são:

- Importação de Bibliotecas Python e preparação do ambiente  
- Importação e Pré-Processamento dos dados do domínio  
- Preparação do Dataset e Dataloader  
- Criação da Rede Neural para Fine Tuning  
- Fine Tuning do Modelo  
- Validação do Desempenho do Modelo  
- Salvando o modelo e artefatos para Inferência no Futuro  


**Dados:**
O dataset originário foi obtido na plataforma kaggle, e é denominado AI vs Human text, contendo mais de 500 mil artigos escritos por humanos ou por IA.

Estruturação:
Em cada linha temos um texto na coluna ```text```, com o valor de 0 na coluna ```generated``` para textos escritos por humanos. Ao contrário, o valor é 1.

Para nosso trabalho, utilizamos 30000 exemplos do dataset.

**Modelo de Linguagem Utilizado:**  
O DistilBERT vai ser utilizado neste projeto. Ele é um modelo transformer criado pela equipe do Hugging Face.

**NOTA**  
Deve-se notar que as saídas do modelo BERT são diferentes do modelo DistilBert implementado pela equipe Hugging Face. Não há `token_type_ids` gerados pelo tokenizer no caso do DistilBert e também as saídas finais da rede diferem.  
Isso será explicado mais adiante no notebook.
