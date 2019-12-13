# Criação e aplicação de modelos

## Login no floydHub
1. Abrir o dashboard na conta do [floydhub](https://floydhub.com), ou
2. Executar no terminal o seguinte comando `floyd login`

## Criar um projecto no floydhub

Para criar um ambiente de trabalho é necessário criar um projecto no floydhub, clonar o repositório que vamos utilizar (fast-style-transfer) e inicializar lá o projecto floydhub criado anteriormente. 

1. Criar projecto [aqui](https://www.floydhub.com/projects/create).
2. Clonar o repositório localmente no computador através do comando `git clone https://github.com/floydhub/fast-style-transfer.git`
3. Entra na directoria `cd fast-style-transfer`
4. Inicializar o projecto floydhub
	`floyd init hjneves/maat_test`

## Aplicar um modelo pré-definido

Neste repositório existem os seguinte modelos de estilo pré-definidos:

|Modelo 			|
|--------|
|rain_princess.ckpt|
|wreck.ckpt|
|la_muse.ckpt|
|udnie.ckpt|
|wave.ckpt|
|scream.ckpt|

Para aplicar o modelo wave.ckpt a uma imagem devem colocar a imagem na pasta `images` e executar o seguinte comando:


```
floyd run --env tensorflow-0.12:py2 \
--data narenst/datasets/neural-style-transfer-pre-trained-models/1:models "python evaluate.py \
--allow-different-dimensions  \
--checkpoint /models/wave.ckpt \
--in-path ./images/ \
--out-path ./output/"
```
Se a directoria `output` não existir deve ser criada, com um ficheiro dummy

Para utilizar outro modelo pré-definido devem substituir `wave.ckpt`por outro modelo na tabela acima.


