# Laboratorio_04

As modificações feitas no código fornecido pelo professor foram as seguintes:
* Foi habilitada a interrupção do PJ1 em Button_int_conf (estava habilitado somente PJ0);
* Em GPIOJ_Handler foi adicionado ACK do PJ1; 
* Foi utilizado o registrador R5, para verificar se houve interrupção (R5=1) e fazer o debouncing do botão, após isso R5 é zerado;
* Em GPIOJ_Handler é desabilitada a interrupção até que seja realizado escrita nos LEDs e feito debouncing no main (para evitar muitas interrupções por repique).

Respondendo a questão do exercício 20, item 5:
– Como é possível identificar a causa da interrupção (botão SW1 ou SW2) na ISR “GPIOJ_Handler”?

R: A causa da interrupção pode ser identificada fazendo uma leitura no registrador GPIORIS da porta J, que armazena o pino responsável pela interrupção, já que a interrupção da porta J é compartilhada com todos os pinos.

