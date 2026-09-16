[![UNIVAS](https://img.shields.io/badge/UNIVAS-Institucional-green)](https://www.univas.edu.br/)
![Status](https://img.shields.io/badge/Exploração_e_Alinhamento_de_Dados-blue)

# Estratégias de Alinhamento de dados para a previsão da velocidade do vento com LiDAR & ERA5 #
Este repositório contém o desenvolvimento de um pipeline computacional para a previsão da velocidade do vento a 100 metros de altura, com foco no entendimento literário e alinhamento de dados pré modelos de aprendizado profundo. 
Esta fase consiste em desenvolver abordagens de alinhamento de dados observacionais de alta resolução (LiDAR) e reanálises atmosféricas globais gratuitas (ERA5) para posteriormente alimentar modelos de Aprendizado Profundo.
.
## 📑 Pilares da Pesquisa ##
A fundamentação técnica deste projeto está dividida em três pilares fundamentais, conforme estabelecido na fase inicial do estudo:
### 1. Previsão da Velocidade do Vento
- Importância: A energia eólica responde por mais de 16% da matriz elétrica brasileira, concentrada majoritariamente no Nordeste. Previsões precisas (horizonte de 12-24h) são críticas para que o Operador Nacional do Sistema (ONS) garanta a estabilidade da rede e gerencie "rampas de vento".
- Falha de Métodos Tradicionais: Modelos estatísticos como ARIMA e SARIMA frequentemente falham por não conseguirem capturar a natureza caótica, não linear e as dinâmicas de microescala das séries temporais de vento.
- Soluções em Deep Learning: Redes LSTM (Long Short-Term Memory) são eficazes por modelarem dependências de longo prazo. Arquiteturas Seq2Seq com mecanismo de atenção superam modelos simples ao priorizar informações relevantes em sequências longas e permitir previsões robustas de múltiplos passos.

### 2. Validação de Reanálises Atmosféricas (ERA5)
- O que é o ERA5: Produzido pelo ECMWF, é a quinta geração de reanálise atmosférica global.
- Funcionamento: Combina observações históricas (satélites, boias, estações) com modelos numéricos através de técnicas de assimilação de dados, fornecendo uma reconstrução contínua da atmosfera desde 1940.
- Limitações: Com resolução espacial de ~31 km, o ERA5 apresenta dificuldades em capturar fenômenos de mesoescala e variações de alta frequência em zonas costeiras, tendendo a subestimar a velocidade do vento nessas regiões.
  
### 3. Fusão de Dados Heterogêneos
- Sinergia LiDAR + ERA5: O projeto investiga a integração de dados observacionais de LiDAR (precisão local, mas custo elevado e escasso) com o ERA5 (ampla cobertura e gratuito).
- Objetivo: Determinar em que medida a base global abundante pode complementar ou substituir a infraestrutura local em regiões sem monitoramento, criando um modelo preditivo com maior generalização.

---

## 🧩 Estratégia de Alinhamento entre as Fontes

Combinar um dado pontual e de alta frequência (LiDAR) com um dado de grade e
frequência mais baixa (ERA5) exige decisões metodológicas explícitas. As
estratégias empregadas nesta fase foram:

1. **Alinhamento temporal**
   *(preencher: como os timestamps de 10 min do LiDAR foram compatibilizados
   com a resolução horária do ERA5 — reamostragem, agregação, interpolação?)*

2. **Alinhamento espacial**
   *(preencher: como foi selecionado o ponto de grade do ERA5 mais próximo à
   estação LiDAR — vizinho mais próximo, interpolação bilinear?)*

3. **Harmonização de unidades e alturas**
   *(preencher: como os dados de diferentes alturas de medição foram
   compatibilizados entre as duas fontes — extrapolação por perfil de
   potência do vento, por exemplo?)*

4. **Métricas de validação do alinhamento**
   *(preencher: quais métricas foram usadas para validar que o alinhamento
   fez sentido fisicamente — correlação entre as séries LiDAR x ERA5,
   diferença média (bias), RMSE entre as fontes antes de qualquer modelo?)*

---

## 📊 Análise Exploratória e Resultados Pré-Modelo

Antes de qualquer modelagem preditiva, esta fase produziu os seguintes
achados sobre o comportamento dos dados:

- **Padrões cíclicos diários:** *(preencher: há variação sistemática por
  horário do dia? A que se atribui — brisa marítima/terrestre, gradiente
  térmico?)*
- **Correlação entre variáveis:** *(preencher: quais variáveis mostraram
  maior relação com a velocidade do vento na altura-alvo?)*
- **Qualidade dos dados:** *(preencher: dados faltantes, outliers,
  inconsistências identificadas e como foram tratados)*
- **Concordância LiDAR x ERA5:** *(preencher: o quanto as duas fontes
  concordam entre si? Isso valida o uso combinado das duas na Fase 2?)*

> Esses resultados são o que orientam diretamente as decisões de modelagem
> da próxima fase — por exemplo, quais variáveis entram no modelo e qual
> tamanho de janela temporal faz sentido testar.

---

## 🎯 Próximos Passos (Fase 2 — em andamento)

- Desenvolvimento de modelo LSTM (uni/bidirecional) como baseline
- Evolução para arquitetura Seq2Seq com mecanismo de atenção
- Avaliação com métricas RMSE/MAE e validação via rolling forecasting
- *(repositório/documentação da Fase 2 será linkado aqui quando disponível)*

---
## 📝 Licença
Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

---

## 📁 Stack Técnica (Fase 1)

`Python` `Pandas` `NumPy` `Matplotlib` `Análise de Séries Temporais`
