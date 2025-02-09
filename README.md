# Controle de Servo Motor com PWM e Interrupções - Como o LED Red da BitDogLab Se Comporta.

Este projeto tem como objetivo controlar o movimento de um servo motor utilizando a placa Raspberry Pi Pico. O servo motor é movido de maneira suave entre os ângulos de 0° e 180°, após as posições iniciais (180°, 90° e 0°), com um ciclo de trabalho (Duty Cycle) ajustado a cada 10ms, utilizando interrupções para garantir precisão no controle. O comportamento do LED vermelho no pino GPIO 13 é controlado da mesma forma, oferecendo uma visualização do processo.

## Funcionamento

O código configura a GPIO 13 da Raspberry Pi Pico para gerar um sinal PWM que controla a intensidade do LED vermelho. A cada 10ms, o ciclo de trabalho do PWM é ajustado de forma incremental, permitindo que a intensidade da luz do LED aumente. Quando a intensidade atinge o valor máximo, o ciclo de trabalho começa a ser reduzido, fazendo a intensidade do LED diminuir até o valor inicial.

### Passos principais do funcionamento:

1. **Configuração do PWM**:
   - A frequência do PWM é configurada para 50Hz, com um período de 20ms.
   - O ciclo de trabalho (Duty Cycle) é controlado por um pulso de 400µs a 2500µs, representando a variação do ângulo do servo, mas também utilizado para controlar a intensidade do LED.

2. **Incremento e Decremento do Pulso**:
   - A cada 10ms, o valor do pulso é ajustado de forma incremental (+5µs), o que faz o servo mover-se gradualmente, ou aumenta a intensidade do LED.
   - Quando o pulso atinge o valor máximo (2500µs), ele começa a ser decrementado, movendo o servo de volta para a posição inicial e diminuindo a intensidade do LED.

3. **Interrupções**:
   - A intensidade é controlada por interrupções, permitindo um controle preciso e regular do LED sem sobrecarregar a CPU.

## Arquivos

- Código principal que configura o PWM e a interrupção para controlar o LED.

## Requisitos

- Wokwi (Plataforma de simulação).
- BitDogLab (Placa de controle).

## Como Usar

1. Conecte o LED à GPIO 13 da Raspberry Pi Pico.
2. Compile o código e faça o upload para a Raspberry Pi Pico.
3. O LED aumentará e reduzirá sua intensidade lentamente, após as intensidades iniciais setadas.

## Autor

Matheus Santos Souza.

## Código Base

Professor Ricardo Menezes Prates [GitHub](https://github.com/rmprates84/pwm_duty_cycle.git)

## Vídeo

[VideoDeApresentacao](https://youtu.be/--G7rcpNSAM)
