# 📊 Análise dos Planos Pré-Pagos da Megaline

Este repositório contém a análise dos planos pré-pagos **Surf** e **Ultimate** da operadora Megaline. O objetivo principal é identificar qual plano gera mais receita e entender o comportamento dos clientes em relação a chamadas, mensagens e uso de internet.

---

## 🎯 Objetivo do Projeto

- Analisar dados de 500 clientes da Megaline, avaliando qual plano (**Surf** ou **Ultimate**) é mais rentável.
- Investigar o comportamento dos usuários quanto ao uso de chamadas, mensagens e internet.
- Realizar testes estatísticos para comparar receitas entre planos e regiões.

---

## 📁 Estrutura dos Dados

O projeto utiliza os seguintes conjuntos de dados:

- **users**: informações dos clientes (`user_id`, nome, idade, cidade, plano, datas de registro e cancelamento)
- **plans**: detalhes dos planos Surf e Ultimate (franquias, valores, custos excedentes)
- **calls**: registros de chamadas realizadas (`call_id`, `user_id`, data, duração)
- **messages**: registros de mensagens enviadas (`message_id`, `user_id`, data)
- **internet**: sessões de uso de internet (`session_id`, `user_id`, data, MB consumidos)

---

## 🧼 Etapas da Análise

### 🔹 Limpeza dos Dados
- Conversão de datas para o formato `datetime`.
- Remoção de registros inválidos (ex: chamadas com duração zero).
- Tratamento de valores ausentes e tipos de dados inadequados.

### 🔹 Enriquecimento
- Cálculo de métricas agregadas por usuário: total de chamadas, duração, mensagens, MB usados, sessões de internet, etc.
- Criação de variáveis auxiliares como tempo de conta ativa e status de churn.

### 🔹 Agregação Mensal
- Consolidação dos dados para obter, por usuário e mês, o total de minutos, mensagens e MB consumidos.

### 🔹 Cálculo da Receita
- Receita mensal calculada considerando franquias, excedentes e mensalidade de cada plano.
- Cálculo automatizado conforme regras do plano, sem valores hardcoded.

---

## 📈 Análise Exploratória

- Estatísticas descritivas e gráficos comparando uso de chamadas, mensagens e internet entre os planos.
- Avaliação da receita mensal por plano e por região.

---

## 🧪 Testes de Hipóteses

- **Surf vs Ultimate**: Teste t de Student para comparar receitas médias entre os planos.
- **NY-NJ vs Outras Regiões**: Teste t para comparar receitas médias por região.

---

## ✅ Principais Resultados

- **Receita**: O plano **Surf** apresentou maior receita média, porém com maior variabilidade. O **Ultimate** mostrou receita mais estável.
- **Comportamento**: O uso de chamadas, mensagens e internet varia entre os planos, mas não há diferença significativa entre regiões.
- **Teste de Hipótese (Surf vs Ultimate)**: As receitas médias são estatisticamente diferentes (valor-p muito baixo, rejeita H₀).
- **Teste de Hipótese (NY-NJ vs Outras Regiões)**: Não há diferença significativa nas receitas médias por região (valor-p alto, não rejeita H₀).

---

## 📌 Tecnologias Utilizadas

- Python (Pandas, NumPy, Matplotlib, Seaborn, SciPy)
- Jupyter Notebook

---
