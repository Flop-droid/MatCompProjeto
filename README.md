# 🎯 Análise do Equilíbrio do Ombro Durante a Pirouette

Este projeto aplica modelagem física e análise computacional para investigar a estabilidade do ombro durante o movimento de pirouette, comum na dança. A partir de dados coletados por sensores inerciais e de um modelo baseado em torques biomecânicos, é possível simular e analisar a dinâmica articular do ombro ao longo do tempo.

---

## 🧠 Objetivo

Modelar e simular o comportamento angular do ombro durante a pirouette com foco na estabilidade, utilizando:

- Regressão Linear para extração e ajuste de parâmetros
- Método de Runge-Kutta de 4ª ordem (RK4) para simulação numérica de equações diferenciais
- Consideração de torques de **rigidez**, **amortecimento** e **gravidade**

---

## ⚙️ Estrutura do Código

- `generate_sample_balance_csv()`: Gera um conjunto de dados simulados de movimento do ombro
- `regressao_linear()`: Aplica regressão linear aos dados coletados
- `metodo_runge_kutta_sistemas_4ordem()`: Resolve um sistema de EDOs com o método RK4
- `sistema_edo_equilibrio_com_gravidade()`: Define a equação diferencial que modela o equilíbrio do ombro
- `main()`: Executa a análise completa — da leitura dos dados à simulação e visualização dos resultados

---

## 🧪 Modelo Físico

A equação que descreve o sistema é dada por:

```I * d²θ/dt² = -kd * dθ/dt - kp * (θ - θₐₗᵥₒ) - m * g * l * sin(θ)```

Onde:

- \( I \): momento de inércia do braço
- \( k_p \): coeficiente de rigidez (torque restaurador)
- \( k_d \): coeficiente de amortecimento
- \( m \): massa do braço
- \( g \): gravidade
- \( l \): distância até o centro de massa
- \( \theta \): ângulo do ombro em relação ao eixo horizontal

---

## 📈 Resultados

O código plota gráficos comparando:

- A evolução do ângulo real (a partir dos dados) e o ângulo simulado (modelo RK4)
- A velocidade angular real e a velocidade simulada
- Métricas de estabilidade como RMSE, desvio médio e velocidade angular máxima

---

## 🛠️ Requisitos

- Python 3.8+
- Bibliotecas:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `scikit-learn`
  - `scipy`
