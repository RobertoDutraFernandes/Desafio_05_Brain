# Desafio_05_Brain
Rede CNN para classificação de tumor cerebral.

# Objetivo:
O 5º e último desafio proposto pelo BRAIN, consiste no desenvolvimento e treinamento de uma rede neural convolucional que será responsavel por identificar ou não a presença de um tumor cerebral em uma tomografia. Para isto foi utilizado um DataSet/DataFrame retirado do kaggle que possui imagens e dados referente a diversas tomografias cerebrais.

# Etapa I - Preparação dos arquivos
Inicialmente é feita a definição das seeds para os parâmetros que serão utilizados no decorrer do notebook, isto garante que seja possível replicar um resultado obtido.

## Divisão das imagens:
Para iniciar, com o DataSet extraido e com o auxílio dos dados do DataFrame, é possível identificar quais imagens possuem ou não a presenção de um tumor, com isso é feita a separação das imagens em 3 pastas, uma para treino (contendo 70% das imagens), uma para teste (contendo 20%) e uma para validação (contendo 10%). Dentro de cada pasta é feita uma divisão das imagens, criando assim 2 classes (pastas), non_tumor e tumor, contendo nelas imagens de tomografias sem tumor e com tumor respectivamente.

## Criação dos sets:
Nesta parte do notebook, efetua-se a criação da função normalizadora e a divisão dos set de treino, teste e validação da rede, que por sua vez é feita de maneira aleatória. Com a função garantimos que os dados de entrada estejam na forma certa e normalizados adequadamente para treinar e testar nossa rede, aqui também é onde é definido o batch size, que basicamente diz a cada quantas imagens nossa rede irá aprender alguma informação.

# Etapa II -  Criação da rede
## Rede CNN criada do zero:
Para treinar a rede, primeiro é necessário criar a arquitetura por trás dela, com isto em mente é necessário definir como a rede CNN irá funcionar. Neste caso em questão foram configuradas 2 camadas convolucionais responsáveis por identificar os padrões/características das imagens, para depois reduzir a imagem com suas características através de 3 camadas lineares, para que na ultima camada linear seja feita a definição da classe.

## Rede CNN criada com transfer learning:
Este tipo de construção criada com o auxílio de transfer learning, consiste em retreinar uma rede já pronta, onde normalmente, são redes que aprenderão em cima de uma grande quantidade de dados e com um arquitetura bem robusta, o que acaba facilitando na resolução de muitos problemas. Com isso em mente, utilizou-se a rede "MobileNetV2" para o caso em questão, sendo necessário apenas redefinir a ultima camada da rede para lidar com o novo problema e congelar as camadas anteriores (mantendo assim o "conhecimento" já obtido).

## Treinamento da rede:
Ambas as arquiteturas foram testadas, porém a que apresentou um maior desempenho foi aquela que utilizou do transfer learning. O loop de treinamento foi feito através da iteração por 20 epochs , dentro de cada uma delas a rede faz a otimização ao visualizar os dados (imagens) dentro do trainset, ao final de cada iteração é feito o cálculo do desempenho da rede segundo o erro do treino e validação, mantendo assim as melhores função de otimização para o modelo salvo. 

## Salvar rede criada:
Para finalizar, a rede é salva segundo os melhores parâmetros obtidos no treinamento, sendo assim, armazena-se a melhor rede possível.

# Etapa III - Testando a performace da rede
Para avaliar o modelo foram realizados 2 teste, no primeiro é plotado algumas imagens de dentro do set de teste com sua respectiva classe, e depois é predito a classe dessas mesma imagens através do modelo, sendo possível verificar a veracidade da predição. Por ultimo é feita uma comparação dentre toda as classes das imagens do set de teste e daquelas classes preditas pela rede em relação as imagens deste mesmo set, ao final disso é plotado uma matriz de confusão para que se possa analisar o resultado da rede. A rede desenvolvida apresenta uma acurácia de aproximadamente 99,72%
