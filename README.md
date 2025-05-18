# Redes-Neurais-2

Sistema de Apoio ao Aprendizado de Matemática com Redes Neurais
Alunos: Cláudio Marcelo Vaz Lima e Beatriz Soutilha Paula | Curso: Pós-graduação em Inteligência Artificial | Disciplina: Redes Neurais Artificiais | Professor: Sérgio Monteiro
Resumo do Projeto
Este projeto desenvolve um sistema inovador para apoiar o aprendizado de matemática básica, utilizando Redes Neurais Artificiais (MLP). O foco está na otimização avançada de hiperparâmetros, uso de callbacks e comparação de otimizadores. O objetivo principal é treinar uma rede capaz de resolver operações matemáticas básicas (adição, subtração, multiplicação e divisão) com dados sintéticos, garantindo robustez e generalização eficaz.
1. Preparação e Validação dos Dados
•	Geração do Dataset: Dataset sintético com 10.000 amostras foi criado, contendo três colunas: número 1, número 2 e código da operação (0 = soma, 1 = subtração, 2 = multiplicação, 3 = divisão). O rótulo é o resultado da operação.
•	Divisão dos Dados:
•	Treinamento: 60%
•	Validação: 20%
•	Teste: 20%
Justificativa: Essa divisão permite o ajuste de hiperparâmetros sem comprometer a avaliação final (teste).
Pré-processamento: Aplicação de normalização dos dados com StandardScaler.
Validação Cruzada: Não foi utilizada K-Fold devido ao tamanho do dataset, mas é recomendada para conjuntos menores ou desbalanceados.
2. Arquitetura da Rede Neural
•	Tipo de Rede: MLP (Perceptron Multicamadas)
•	Camadas: 3 camadas densas (fully connected)
•	Funções de Ativação Testadas: ReLU, LeakyReLU e Tanh
•	Regularização:
•	Dropout aplicado para evitar overfitting
•	Regularização L2 nos pesos
Resultados: A função ReLU obteve o melhor desempenho em combinação com L2 e Dropout de 20%.
3. Otimização de Hiperparâmetros
•	Ferramenta Utilizada: Keras Tuner (RandomSearch)
•	Hiperparâmetros Otimizados:
•	Número de neurônios por camada
•	Taxa de aprendizado
•	Coeficientes de regularização
•	Função de ativação
Otimizadores Testados: Adam (referência), RMSprop, Nadam, SGD com momentum
Critérios de Avaliação: Loss (MSE) e MAE (Erro Absoluto Médio)
Análise: RMSprop e Nadam apresentaram desempenho comparável ao Adam. O SGD demonstrou convergência mais lenta, mas estável.
4. Callbacks Implementados
•	EarlyStopping: Interrompeu o treinamento automaticamente ao detectar ausência de melhoria no val_loss.
•	ModelCheckpoint: Salvou o modelo com melhor desempenho durante o treinamento.
•	TensorBoard: Log das métricas para análise visual.
•	Callback Personalizado: Exibiu o MAE ao final de cada época.
5. Treinamento e Avaliação
•	Desempenho Final no Teste:
•	Loss (MSE): ex: 0.0012
•	MAE: ex: 0.0204
Testes Adicionais: Números negativos e divisão por zero (com tratamento). O modelo apresentou boas previsões mesmo em casos não vistos antes.
Análise de Overfitting: O gráfico de perda de treino/validação mostrou convergência consistente. Dropout e EarlyStopping foram cruciais para evitar overfitting.
Conclusão
O modelo MLP desenvolvido demonstrou elevada capacidade de aprendizado e generalização para operações matemáticas básicas. A combinação de técnicas como otimização de hiperparâmetros, regularização e callbacks garantiu robustez ao processo. Os resultados destacam uma precisão elevada e baixa margem de erro, indicando o potencial do sistema para aplicações educacionais automatizadas.
Recomendações Futuras
•	Aumentar a diversidade do dataset (ex.: incluir frações, potências e equações)
•	Explorar modelos sequenciais (RNNs) para problemas mais complexos
Desenvolver uma interface interativa e amigável par
