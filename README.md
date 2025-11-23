### Documentação Técnica – Modelo de Predição de Mudança de Carreira

## 1. Contextualização do Problema

O mercado de trabalho contemporâneo passa por mudanças profundas, impulsionadas por fatores como:

- Avanços tecnológicos (IA, automação, big data)
- Evolução do perfil de habilidades exigidas
- Emergência de novas profissões e redução de funções tradicionais
- Crescente rotatividade e incertezas no planejamento de carreira

Nesse contexto, muitos profissionais enfrentam um problema central: **não possuem clareza sobre a direção futura de suas carreiras**.  
Essa falta de previsibilidade compromete:

- a tomada de decisão sobre mudança profissional,
- o planejamento educacional e financeiro,
- a retenção de talentos dentro das organizações,
- a compreensão dos fatores que influenciam uma transição de carreira.

## 2. Descrição da Solução (Protótipo)

A solução é composta por dois elementos principais:

- Modelo preditivo responsável por calcular a probabilidade de mudança de carreira.
- API de integração que disponibiliza essa previsão para o backend.

A base de dados utilizada é limitada em volume e diversidade. Por isso, o modelo deve ser interpretado como um **MVP acadêmico**, cujo desempenho está condicionado à qualidade dos dados.

Aplicamos boas práticas visando:

- coerência estatística,
- estabilidade,
- interpretabilidade,
- simplicidade na integração com o backend.

## 3. Processo Analítico e Justificativas Técnicas

### 3.1 Análise Exploratória e Estudo de Correlações

Foram avaliadas diversas características da base, utilizando:

- Correlação de Pearson (relações lineares)
- Correlação de Spearman (relações monotônicas)
- Correlação de Kendall (variáveis ordinais)

Também verificamos:

- duplicidades,
- multicolinearidade,
- possíveis vazamentos de informação,
- redundância entre atributos.

**Conclusão da EDA:** algumas variáveis apresentaram relação significativa com a variável-alvo *Likely to Change Occupation*, como:

- Job Satisfaction — correlação negativa forte
- Career Change Interest — correlação positiva moderada
- Salary — correlação negativa moderada

### 3.2 Primeiro Modelo (Usando Todas as Variáveis)

O primeiro modelo foi treinado usando todas as variáveis disponíveis.

As métricas avaliadas incluíram:

- Acurácia
- AUC-ROC
- Importância das Features

**Resultado:** acurácia extremamente alta (aprox. 100%), indicando:

- overfitting,
- ruído,
- possível vazamento de informação.

### 3.3 Seleção das Variáveis Mais Relevantes

Após análise estatística e alinhamento com regras de negócio, selecionamos 6 variáveis finais:

- Job Satisfaction
- Salary
- Field of Study (Class)
- Current Occupation (Class)
- Education Level (Class)
- Age

## 4. Modelo Final Selecionado

O modelo final utilizado foi o **Random Forest Classifier**, escolhido por:

- boa performance em bases pequenas,
- robustez para padrões não lineares,
- não exigir normalização,
- interpretabilidade por importance scores,
- estabilidade após tuning simples,
- leveza e eficiência no deploy.

## 5. Métricas do Modelo Final

- **Acurácia:** ~ 89%
- **AUC-ROC:** ~ 0.90

**Interpretação:**

- Acurácia de 89% indica que o modelo acerta aproximadamente nove de cada dez previsões.
- AUC-ROC de 0.90 indica excelente capacidade de distinguir quem tem maior propensão à mudança de carreira.

