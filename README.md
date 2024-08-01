# Desafio_05_Brain
Rede Neural CNN para classificação de tumor cerebral.

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

## Rede CNN criada com tranfer learning:

## Salvar rede criada:

# Etapa III - Testando a performace da rede

