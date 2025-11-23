### Documentação Técnica – Modelo de Predição de Mudança de Carreira
## 1. Contextualização do Problema

O mercado de trabalho contemporâneo passa por mudanças profundas, impulsionadas por fatores como:

- Avanços tecnológicos (IA, automação, big data)

- Evolução do perfil de habilidades exigidas

- Emergência de novas profissões e redução de funções tradicionais

Crescente rotatividade e incertezas no planejamento de carreira

Nesse contexto, muitos profissionais enfrentam um problema central: não possuem clareza sobre a direção futura de suas carreiras.
Essa falta de previsibilidade compromete:

a tomada de decisão sobre mudança profissional,

o planejamento educacional e financeiro,

a retenção de talentos dentro das organizações,

a compreensão dos fatores que influenciam uma transição de carreira.

Como resposta, desenvolvemos uma solução baseada em inteligência artificial capaz de estimar a probabilidade de mudança de carreira, considerando variáveis profissionais e socioeconômicas.

2. Descrição da Solução (Protótipo)

A solução é composta por dois elementos principais:

Modelo Preditivo responsável por calcular a probabilidade de mudança de carreira.

API de Integração, que disponibiliza essa previsão para ser consumida pelo backend.

A base de dados utilizada é limitada em volume e diversidade. Por isso, o modelo funciona como um MVP acadêmico, cujo desempenho está diretamente ligado à qualidade dos dados.

Mesmo assim, aplicamos boas práticas visando:

coerência estatística,

estabilidade,

interpretabilidade,

simplicidade de integração com o backend.

3. Processo Analítico e Justificativas Técnicas
3.1 Análise Exploratória e Estudo de Correlações

Foram utilizadas técnicas como:

Correlação de Pearson (relações lineares)

Correlação de Spearman (relações monotônicas)

Correlação de Kendall (variáveis ordinais)

Também verificamos:

duplicidades,

multicolinearidade,

vazamento de informação,

redundância entre atributos.

Conclusões da EDA:

Apesar das mais de 20 variáveis da base, apenas algumas apresentaram relação significativa com a variável alvo:

Job Satisfaction — correlação negativa forte

Career Change Interest — correlação positiva moderada

Salary — correlação negativa moderada

As demais foram consideradas irrelevantes ou ruidosas.

3.2 Primeiro Modelo: Todas as Variáveis

Treinamos um modelo inicial com todas as colunas disponíveis. Avaliamos:

Acurácia
