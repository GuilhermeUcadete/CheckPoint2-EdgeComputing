# CheckPoint2-EdgeComputing
Check Point 1 - Edge Computing | RM558418-Guilherme Ulacco | RM556517-Matheus Hostim | RM555372-Enzo Bonacasata | RM555351-Henrique Lomaski | RM558932-Luiz Guilherme | RM559097 Vinicius Augusto

Este código é um exemplo de um programa para Arduino que utiliza um sensor de luminosidade (LDR), um sensor de temperatura, um sensor de umidade, LEDs e um buzzer para monitorar e exibir informações sobre a temperatura, umidade e luminosidade do ambiente em um display LCD.

Vou explicar as principais partes do código:

1-Definição dos pinos: Aqui são definidos os pinos utilizados para conectar os componentes ao Arduino.
2-Inicialização do LCD: O objeto LiquidCrystal é inicializado com os pinos específicos para o display LCD.
3-Configuração do ambiente no setup(): No método setup(), os pinos dos LEDs e do buzzer são configurados como saídas, e o display LCD é inicializado.
4-Loop principal (loop()): Neste loop, o programa realiza as seguintes ações:a. Lê os valores do sensor de luminosidade, sensor de umidade e sensor de temperatura.b. Exibe a temperatura atual no display LCD, indicando se está baixa, ok ou alta.c. Exibe a umidade atual no display LCD, indicando se está baixa, ok ou alta.d. Atualiza os LEDs e o buzzer com base no valor lido pelo sensor de luminosidade. Se o ambiente estiver escuro, acende o LED vermelho e ativa o buzzer; se estiver em meia luz, acende o LED amarelo; se estiver claro, acende o LED verde.e. Aguarda um intervalo de tempo antes de repetir o loop.
5-Função readTemperature(): Esta função realiza a leitura do sensor de temperatura e retorna o valor convertido para graus Celsius.

Basicamente, o código monitora continuamente as condições do ambiente e exibe informações relevantes no display LCD, além de controlar os LEDs e o buzzer com base na luminosidade detectada.





