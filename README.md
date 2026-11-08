<p align="center"><img src="logo-darosa.png" width="96" alt="Logo daRosa"></p>

# daRosa Modelamento 3D

Editor 3D simples, que roda no navegador, para criar peças para impressão 3D. Ele foi feito pensando na Bambu Lab A1 mini (mesa de 180 × 180 × 180 mm).

Você desenha a peça na vista de cima, acompanha o resultado numa prévia 3D e exporta um **STL** pronto para o fatiador, como o Bambu Studio.

## O que dá para fazer

- **Bloco base**
  - Largura, profundidade, altura e cantos arredondados.
  - Contorno livre, editando os nós.
- **Formas**: retângulo, círculo, polígono (desenhado ponto a ponto), texto e imagem.
  - Cada forma pode ser um **rebaixo** (corte) ou um **relevo** (adicionar).
  - No rebaixo, dá para definir o fundo e o **topo do corte**, para que ele não atravesse os relevos.
  - Arraste com o mouse para mover, redimensionar e editar nós.
  - Cada forma tem um **ponto de ancoragem**, com 9 posições, e um **ângulo de rotação**.
- **Texto**: 14 fontes, entre elas sem serifa, com serifa, estêncil e cursivas. Aceita acentos e várias linhas.
- **Imagem → relevo**: importa uma imagem e transforma as partes escuras em forma. Ajustes disponíveis:
  - limiar;
  - suavização;
  - remoção de pontinhos;
  - inverter;
  - ignorar a moldura.
- **Projetos salvos no navegador**: abrir, duplicar, excluir, exportar e importar `.json` e fazer backup de todos.
- **STL fechado**: as operações booleanas usam o [manifold-3d](https://github.com/elalish/manifold).
- Aviso quando a peça passa do tamanho da mesa da impressora.

## Como usar

É um único arquivo HTML. As bibliotecas (three.js, manifold-3d, opentype.js e as fontes) vêm por CDN, então é preciso ter internet.

Sirva a pasta com qualquer servidor estático. Por exemplo:

```bash
python -m http.server 8765
```

Depois abra <http://localhost:8765/editor3d.html>.

## Backup dos projetos

Os projetos ficam guardados no `localStorage` do navegador. Para levá-los a outro navegador, ou para não perdê-los:

1. No navegador de origem, vá em **📁 Meus projetos → Baixar backup de todos**.
2. No navegador de destino, vá em **📁 Meus projetos → Importar .json** e escolha o arquivo de backup.

## Dicas de impressão (bico 0,4 mm)

- Use letras com 5 mm ou mais de altura.
- Para gravar um texto, um rebaixo de 0,6 a 1 mm já basta.
- Detalhes com menos de cerca de 0,5 mm de largura tendem a sumir na impressão.
