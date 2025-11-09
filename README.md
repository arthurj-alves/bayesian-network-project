# 🌐 Projeto: Redes Bayesianas – Comparação entre Modelo Aprendido e Modelo Asia Original

Este projeto tem como objetivo **comparar o desempenho de uma rede bayesiana aprendida por dados reais** (via algoritmo Hill Climbing) com o **modelo Asia original**, amplamente utilizado como referência em inferência probabilística.

A análise foi conduzida em Python utilizando a biblioteca **pgmpy**, com ênfase na **inferência de probabilidade condicional**, **avaliação preditiva** e **análise de overfitting** em diferentes tamanhos de amostra.

---

## 📘 Contexto

As **redes bayesianas** são modelos probabilísticos que representam relações de dependência entre variáveis aleatórias.  
Neste projeto, exploramos o clássico **modelo Asia**, que simula diagnósticos médicos relacionados a bronquite, tuberculose e câncer de pulmão.

A partir desse modelo, realizamos duas abordagens:

1. **Rede Original (Asia)** – modelo teórico, com estrutura e probabilidades fixas.  
2. **Rede Aprendida (Hill Climbing)** – modelo estimado diretamente a partir de dados (`asia10K.csv`), usando aprendizado estrutural e de parâmetros.

---

## 🧩 Estrutura do Projeto

```

📁 RedeBayesiana_Asia/
│
├── 📄 asia10K.csv              # Base de dados utilizada
├── 📓 notebook.ipynb           # Código principal do experimento
├── 🧠 discussion_results.md     # Discussão e conclusões dos resultados
├── 📈 imagens/                 # Gráficos e visualizações (opcional)
└── README.md                   # Este arquivo

```


---

## 🧠 Metodologia

1. **Carregamento e preparação dos dados**
   - O dataset `asia10K.csv` foi convertido para valores binários (`0 = no`, `1 = yes`).

2. **Aprendizado estrutural**
   - Utilizou-se o algoritmo **Hill Climbing (HC)** com o critério de **Bayesian Information Criterion (BIC)**.

3. **Treinamento e inferência**
   - Estimativa dos parâmetros via **Maximum Likelihood Estimator**.
   - Inferência probabilística usando o método **Variable Elimination**.

4. **Comparação de desempenho**
   - Foram medidas as métricas de **acurácia**, **precisão**, **recall** e **F1-score**.
   - A comparação foi feita entre a rede **HC** e a **Asia original**, com **amostras pequenas (n=100)** e **grandes (n=3000)**.

---

## 📊 Resultados Principais

| Modelo | Amostra | Accuracy | Precision | Recall | F1-score |
|---------|----------|-----------|------------|----------|-----------|
| Hill Climbing | 100 | 0.8667 | 1.0000 | 0.7647 | 0.8667 |
| Asia Original | 100 | 0.5667 | 0.5667 | 1.0000 | 0.7234 |
| Hill Climbing | 3000 | 0.8500 | 0.8588 | 0.8007 | 0.8288 |
| Asia Original | 3000 | 0.1500 | 0.1565 | 0.1993 | 0.1753 |

---

## 💬 Discussão

Os resultados mostram que a **rede aprendida por Hill Climbing** se ajusta muito melhor aos dados, apresentando alta acurácia e equilíbrio entre precisão e recall.  
A **rede Asia original**, por outro lado, tem desempenho inferior, pois foi construída com base em probabilidades teóricas e não representa fielmente as distribuições empíricas do dataset.

No caso de **poucos dados**, observou-se **precisão perfeita (1.0)**, o que sugere **overfitting**. O modelo se tornou excessivamente específico aos padrões de treino, perdendo parte da capacidade de generalizar para novos casos.

Com o aumento da amostra, a rede aprendida manteve desempenho estável e consistente, enquanto a rede original teve queda acentuada, revelando seu desalinhamento com os dados observados.

---

## 🧾 Conclusão

- A rede Hill Climbing mostrou-se **superior em desempenho preditivo**, mas sujeita a overfitting em bases pequenas.  
- A rede Asia original manteve coerência causal, porém **falhou em previsão**, reforçando a diferença entre **modelos explicativos** e **modelos estatísticos ajustados**.  
- A ampliação da amostra melhora a generalização e aproxima o modelo aprendido de uma estrutura mais realista.  

---

## 👨‍💻 Autor

**ARTHUR JORGE**  
Estudante de Engenharia de Sistemas – UFMG  
Contato: [arthurjorgeac@gmail.com]

---

## 📜 Licença

Este projeto é distribuído sob a licença MIT.  
Sinta-se à vontade para usar, modificar e compartilhar.

---
