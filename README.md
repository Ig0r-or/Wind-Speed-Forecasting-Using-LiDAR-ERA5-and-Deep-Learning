[![UNIVAS](https://img.shields.io/badge/UNIVAS-Institucional-green)](https://www.univas.edu.br/)

# Previsão da Velocidade do Vento usando DeepLearning e Dados Heterogêneos #
Este repositório contém o desenvolvimento de um pipeline computacional para a previsão da velocidade do vento a 100 metros de altura, com foco na costa leste do Maranhão
. O estudo utiliza uma abordagem de Aprendizado Profundo alimentada pela fusão de dados observacionais de alta resolução e reanálises atmosféricas globais
.
## 📑 Pilares da Pesquisa (Revisão de Literatura) ##
A fundamentação técnica deste projeto está dividida em três pilares fundamentais, conforme estabelecido na fase inicial do estudo:
### 1. Previsão da Velocidade do Vento
Importância: A energia eólica responde por mais de 16% da matriz elétrica brasileira, concentrada majoritariamente no Nordeste
. Previsões precisas (horizonte de 12-24h) são críticas para que o Operador Nacional do Sistema (ONS) garanta a estabilidade da rede e gerencie "rampas de vento"
.
Falha de Métodos Tradicionais: Modelos estatísticos como ARIMA e SARIMA frequentemente falham por não conseguirem capturar a natureza caótica, não linear e as dinâmicas de microescala das séries temporais de vento
.
Soluções em Deep Learning: Redes LSTM (Long Short-Term Memory) são eficazes por modelarem dependências de longo prazo
. Arquiteturas Seq2Seq com mecanismo de atenção superam modelos simples ao priorizar informações relevantes em sequências longas e permitir previsões robustas de múltiplos passos
.
### 2. Validação de Reanálises Atmosféricas (ERA5)
O que é o ERA5: Produzido pelo ECMWF, é a quinta geração de reanálise atmosférica global
.
Funcionamento: Combina observações históricas (satélites, boias, estações) com modelos numéricos através de técnicas de assimilação de dados, fornecendo uma reconstrução contínua da atmosfera desde 1940
.
Limitações: Com resolução espacial de ~31 km, o ERA5 apresenta dificuldades em capturar fenômenos de mesoescala e variações de alta frequência em zonas costeiras, tendendo a subestimar a velocidade do vento nessas regiões
.
### 3. Fusão de Dados Heterogêneos
Sinergia LiDAR + ERA5: O projeto investiga a integração de dados observacionais de LiDAR (precisão local, mas custo elevado e escasso) com o ERA5 (ampla cobertura e gratuito)
.
Objetivo: Determinar em que medida a base global abundante pode complementar ou substituir a infraestrutura local em regiões sem monitoramento, criando um modelo preditivo com maior generalização
.
## 📝 Licença
Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.
