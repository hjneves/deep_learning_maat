# Criação e aplicação de modelos

## Login no floydHub
1. Abrir o dashboard na conta do [floydhub](https://floydhub.com), ou
2. Executar no terminal o seguinte comando `floyd login`

## Criar um projecto no floydhub

Para criar um ambiente de trabalho é necessário criar um projecto no floydhub, clonar o repositório que vamos utilizar (fast-style-transfer) e inicializar lá o projecto floydhub criado anteriormente. 

1. Criar projecto com o nome `maat` [aqui](https://www.floydhub.com/projects/create).
2. Clonar o repositório localmente no computador através do comando `git clone https://github.com/floydhub/fast-style-transfer.git`
3. Entrar na directoria `cd fast-style-transfer`
4. Inicializar o projecto floydhub
	`floyd init hjneves/maat`

## Aplicar um modelo pré-definido

Neste repositório existem os seguintes modelos de estilo pré-definidos:

|Modelo 			|
|--------|
|rain_princess.ckpt|
|wreck.ckpt|
|la_muse.ckpt|
|udnie.ckpt|
|wave.ckpt|
|scream.ckpt|

Por exemplo, para aplicar o modelo `wave.ckpt` a uma imagem devem colocar a imagem na pasta `images` e executar o seguinte comando:


```
floyd run --env tensorflow-0.12:py2 \
--data narenst/datasets/neural-style-transfer-pre-trained-models/1:models "python evaluate.py \
--allow-different-dimensions  \
--checkpoint /models/wave.ckpt \
--in-path ./images/ \
--out-path ./output/"
```
Se a directoria `output` não existir deve ser criada, com um ficheiro dummy

Para utilizar outro modelo pré-definido devem substituir `wave.ckpt`por outro modelo da tabela acima.

## Treinar um novo estilo
Para criar um estilo com base numa nova imagem, é necessário treinar um novo modelo. A imagem será interpretada como o estilo a transferir para outra imagem. O modelo usado é o VGG19. 
O comando a executar é o seguinte:
```
floyd run --env tensorflow-0.12:py2 \
 --data narenst/datasets/coco-train-2014/1:images \
 --data narenst/datasets/neural-style-transfer-pre-trained-models/1:models \
 --data floydhub/datasets/imagenet-vgg-verydeep-19/3:vgg \
 "python style.py \
 --vgg-path /vgg/imagenet-vgg-verydeep-19.mat \
 --train-path /images/train2014 \
 --style style/imageForStyle.jpg \
 --epoch 2 \
 --total-iterations 500 \
 --checkpoint-dir ./checkpoints"
 ```

Criar a directoria `checkpoints`com um ficheiro dummy, caso não exista.
Criar a directoria `style` e colocar lá uma imagem que vai ser usada como estilo.

Substituir no script o nome `imageForStyle.jpg`pelo nome do ficheiro da imagem

`--total-iterations`define o nº de iterações para o treino do modelo. Um maior nº de iterações leva a uma melhor apreensão do estilo da imagem

Outros parâmetros podem ser consultados no script `style.py`ex.

`--style-weight`determina o peso da imagem de style no treino [1e2 por defeito]

`--content-style`determina o peso das imagens de conteúdo no treino [1.5e1 por defeito]

Este comando vai desencadear um job floydhub que após terminar pode ser usado como modelo de estilo no ponto seguinte.

 ## Aplicar o novo estilo a outras imagens
 Para aplicar o modelo de estilo treinado no ponto anterior deve ser executado o seguinte comando:

```
floyd run --env tensorflow-0.12:py2 \
  --data hjneves/projects/maat/53/:input "python evaluate.py \
  --allow-different-dimensions  \
  --checkpoint /input/checkpoints/fns.ckpt \
  --in-path ./images/ \
  --batch-size 1 \
  --out-path ./output/"
```
Alterar o parametro `--data` para o job gerado no-ponto anterior. Por ex. `hjneves/projects/maat/80/`

Colocar uma imagem para aplicar estilo na directoria `images`

**Nota**: Com o free tier do FloydHub existem limitações no tamanho das imagens a usar como input. Usar imagens até 1024px width.
