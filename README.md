# Controle de Servo Motor com PWM e Interrupções - Como o LED Red da BitDogLab Se Comporta.

Este projeto tem como objetivo controlar o movimento de um servo motor utilizando a placa Raspberry Pi Pico. O servo motor é movido de maneira suave entre os ângulos de 0° e 180°, após as posições iniciais (180°, 90° e 0°), com um ciclo de trabalho (Duty Cycle) ajustado a cada 10ms, utilizando interrupções para garantir precisão no controle. Dessa forma, aplicou-se tais condições ao led vermelho no pino GPIO 13 para visualizar seu comportamento.

## Funcionamento

O código configura a GPIO 13 da Raspberry Pi Pico para gerar um sinal PWM que controla o Led vermelho. A cada 10ms, o ciclo de trabalho do PWM é ajustado de forma incremental, permitindo que aumente a intensidade de sua luz. Quando o led atinge a intensidade máxima de acordo com wrap, ele começa a reduzir a intensidade até ponto incial.

### Passos principais do funcionamento:

1. **Configuração do PWM**:
   - A frequência do PWM é configurada para 50Hz, com um intervalo de 20ms (periodo de 20ms).
   - O ciclo de trabalho (Duty Cycle) é controlado por um pulso de 400µs a 2500µs, representando as posições de 0° a 180° do servo, no Led representa intensidade.

2. **Incremento e Decremento do Pulso**:
   - A cada 10ms, o valor do pulso é ajustado de forma incremental (+5µs), o que faz o servo mover-se gradualmente, no Led incrimenta intensidade, pois o pulso do PWM está aumentado.
   - Quando o pulso atinge o valor máximo (2500µs), ele começa a ser decrementado, movendo o servo de volta para a posição inicial (0°), no Led decrementa intensidade, pois o pulso do PWM esta diminuindo.

3. **Interrupções**:
   - A intensidade é controlada por interrupções, o que permite um controle preciso e regular do Led sem consumir recursos excessivos da CPU.

## Arquivos

- Código principal que configura o PWM e a interrupção para controlar o led.

## Requisitos

- Wokwi.
- BitDogLab.

## Como Usar

1. Conecte o led à GPIO 13 da Raspberry Pi Pico.
2. Compile o código e faça o upload para a Raspberry Pi Pico.
3. O led almentara e reduzira sua intensidade lentamente, após as intensidades iniciais setadas.

## Autor

Matheus Santos Souza.

## Código Base

Professor Ricador Menezes Prates [GitHub](https://github.com/rmprates84/pwm_duty_cycle.git)

## Video

[VideoDeApresentacao](https://youtu.be/--G7rcpNSAM)


