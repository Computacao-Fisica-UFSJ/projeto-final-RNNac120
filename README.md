[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/bQrFkq0H)
# Simulador de arrombamento de fechadura
## Contextualização, aplicação e motivação
### Contextualização
Diferente do nosso primeiro trabalho, agora simularemos o sistema de arrombamento de fechaduras do The Elder Scrolls IV: Oblivion (2006), da Bethesda. Agora, o processo é ligeiramente diferente:
- Você testa se o pino está na posição correta (levanta uma das chaves).
    - Se estiver, você gira o potenciômetro e ele acusará se o pino está na posição certa ou não. Se estiver, você avança para o próximo pino, e continua avançando até de fato arrombar a fechadura.
    - Se você acabar girando o potenciômetro e o pino estiver na posição errada, você volta para o início.

Igual ao primeiro trabalho, também há botões para se selecionar a dificuldade que deseja, e essa dificuldade é traduzida para quantos pinos são necessários para destravar a fechadura. As cores verde, amarelo e vermelho, acionadas pelos botões, indicam as dificuldades fácil, média e difícil, respectivamente.
### Aplicação
Esse projeto é uma boa chance para aprender a mexer em dispositivos que transformam sinais analógicos, do "mundo real", em sinais digitais; isso é feito por meio dos botões e dos potenciômetros. Além disso, é uma boa oportunidade para se mexer com comunicação de um dispositivo com a placa Arduino por meio do protocolo I<sup>2</sup>C por conta da tela de LCD.
## Lista de materiais
Diferente do primeiro trabalho, neste utilizamos uma chave DIP -- uma série de interruptores -- que simula a sequência correta de pinos a ser arrombada. Por exemplo, por meio de código pode ser definido que a sequência correta de pinos é 2314, logo, seria necessário ativar as chaves nessa sequência. Além disso, no lugar dos potenciômetros de pressão e torque, utilizamos agora uma célula de carga, que fica responsável por detectar uma pressão em cima dela, que seria análoga 
| Material                | Quantidade | Imagem |
|-------------------------|------------|--------|
| Placa Arduino Uno R3    | 1          |<picture><source srcset="/assets/images/arduino.png" media="(orientation: portrait)" /><img src="https://datacapturecontrol.com/products/static/images/product-references/microcontrollers/atmega328p-uno-r3/atmega328p-uno-r3-listing.png" alt="Placa Arduino Uno R3" width="250"/></picture>|
| *Breadboard*            | 1          |<picture><source srcset="/assets/images/arduino.png" media="(orientation: portrait)" /><img src="https://tinycircuits.com/cdn/shop/products/ASR00044-01.png?v=1674589122" alt="Breadboard" width="250" /></picture>|
| Potenciômetro           | 2          |<picture><source srcset="/assets/images/arduino.png" media="(orientation: portrait)" /><img src="https://cdn.awsli.com.br/2798/2798180/produto/336250708/8fb42bbe73b9a436a4a1b86bf6e3071d-2pktor61yq.png" alt="Potenciômetro" width="250"/></picture>|
| Resistor 220 $$\ohm$$   | 3          |<picture><source srcset="/assets/images/arduino.png" media="(orientation: portrait)" /><img src="https://www.tandyonline.com/media/catalog/product/cache/d24a34bded6d2df740ef66d66d2112c9/2/7/271-1313-220r-carbon-resistors.png" alt="Resistor" width="250"/></picture>|
| Servo motor SG90        | 1          |<picture><source srcset="/assets/images/arduino.png" media="(orientation: portrait)" /><img src="https://d229kd5ey79jzj.cloudfront.net/788/images/788_1_X.png?20250730165301" alt="Resistor" width="250"/></picture> |
| Grove LCD RGB Backlight | 1          |<img src="https://cdn-reichelt.de/bilder/web/xxl_ws/A300%2F104030001_1.png?type=ProductXxl&" width="250" height="250" />        |
| LED vermelho, verde e amarelo            | 1 de cada          | <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/b011dd74-508e-4bcd-b4c6-c49543aec371" /> |
| Chave DIP com 10 interruptores          | 1         | <img width="250" height="250" alt="image" src="https://cdn.awsli.com.br/2500x2500/2723/2723924/produto/273276472/92582ee1-8dda-4293-a9ea-dc4d21f6e969-nu2r2wkm4l.png" /> |
| Célula de carga          | 1         | <img width="250" height="250" alt="image" src="https://d229kd5ey79jzj.cloudfront.net/886/images/886_1_H.png" /> |
| Conector de emenda de duas vias          | 3         | <img width="250" height="250" alt="image" src="https://d229kd5ey79jzj.cloudfront.net/956/images/956_1_H.png" /> |
## Montagem
### Diagrama
O seguinte diagrama foi feito em Fritzing 1.0.1 e mostra como deve ficar a montagem do projeto.

<img width="500" height="500" alt="skyrim_bb" src="https://github.com/user-attachments/assets/0346cf57-bee4-4a6a-9b43-88fd034e1c17" />

### Foto da montagem
![IMG-20251111-WA0035](https://github.com/user-attachments/assets/8f474f56-76d1-4940-89d3-b088ccd831f7)

## Problemas encontrados
Os problemas foram basicamente os mesmos do primeiro. O adicional foi a célula de carga:
### Célula de carga
- É necessário calibrar a célula de carga para que ela registre o peso correto imposto nela, e essa calibragem pode levar um tempo considerável da montagem do projeto.
### Botão
- É necessário fazer o *debounce* no código para evitar alternância muito rápida entre 0 e 1, impedindo um valor exato para ser exato.
### Tela LCD
- A qualidade dos cabos e a conexão deles na tela podem acabar fazendo com que lixo seja transmitido ao invés de um caractere, tornando o projeto inutilizável, sendo necessário desligar e ligar a placa.
## Referências
- https://www.robocore.net/sensor-robo/celula-de-carga-50kg?srsltid=AfmBOopS0AHtNsg180NE8FBlewqBJEIo9beVb6j75O-aJlPdHVUcDLDd
