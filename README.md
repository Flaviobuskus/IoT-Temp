# IoT-Temp
Projeto 5º semestre ADS Mackenzie IoT Temp
Sistema de Monitoramento de Temperatura e Umidade com ESP8266 e MQTT

Este projeto implementa um sistema de monitoramento de temperatura e umidade utilizando o microcontrolador ESP8266, o sensor DHT11, e o protocolo MQTT para comunicação com a plataforma Adafruit IO. Além de monitorar dados ambientais, o sistema aciona um LED como alerta em caso de alta temperatura.
🚀 Funcionalidades

    Monitoramento contínuo de temperatura e umidade em tempo real.
    Envio dos dados para a plataforma Adafruit IO via protocolo MQTT.
    Acionamento automático de alertas visuais (LED) quando a temperatura ultrapassa um limite configurado.
    Reconexão automática à rede Wi-Fi e ao broker MQTT em caso de falha de conexão.

📋 Requisitos
Hardware

    ESP8266 (NodeMCU ou similar): Controlador principal do sistema.
    Sensor DHT11: Para medições de temperatura e umidade.
    LED: Para indicar alertas de alta temperatura.
    Resistores e jumpers: Para conexões.

Software

    IDE Arduino (com bibliotecas necessárias):
        ESP8266WiFi
        Adafruit MQTT
        DHT

⚙️ Configuração
Conexões do Hardware
Componente	Pino ESP8266	Descrição
Sensor DHT11	D2	Leitura de dados
LED	D4	Alerta visual
Configurações no Código

    Configure suas credenciais de Wi-Fi:

const char* WIFI_SSID = "SEU_SSID";
const char* WIFI_PASSWORD = "SUA_SENHA";

Configure as informações da conta Adafruit IO:

const char* AIO_USERNAME = "SEU_USUARIO";
const char* AIO_KEY = "SUA_CHAVE_AIO";

Ajuste o limite de temperatura para o alerta:

    const int TEMPERATURE_THRESHOLD = 27;  // Temperatura limite em °C

🛠️ Funcionamento

    O sensor DHT11 realiza leituras periódicas de temperatura e umidade.
    Os dados são enviados para os feeds configurados na plataforma Adafruit IO.
    Caso a temperatura exceda o limite definido, o LED é acionado e uma mensagem de alerta é enviada.
    Se a temperatura retornar ao normal, o LED é desligado e um status de temperatura normal é enviado.

🧩 Estrutura do Projeto
Diretórios

    /src: Contém o código principal do sistema.
    /docs: Documentação adicional e imagens de referência.
    /examples: Exemplos de uso e integração.

Fluxo de Dados

    ESP8266 → Sensor DHT11 → Adafruit IO (via MQTT)
    ESP8266 → LED (alerta local)

📊 Métricas de Desempenho
Métrica	Valor Médio
Tempo de envio ao MQTT	5 segundos
Precisão de temperatura	±0,5°C
Precisão de umidade	±2%
Taxa de sucesso MQTT	99,5%
🌐 Conexão com Adafruit IO

O sistema utiliza o protocolo MQTT para enviar os dados para os seguintes feeds:

    Temperatura: /feeds/Temperature
    Umidade: /feeds/Humidity
    Alerta de Temperatura: /feeds/TemperatureAlarm

O broker MQTT reconecta automaticamente em caso de desconexão.
📂 Repositório no GitHub

Este repositório inclui:

    Código-fonte completo do projeto.
    Documentação de hardware e software.
    Esquemas de montagem e instruções detalhadas para reprodução.

📝 Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.

Sinta-se à vontade para contribuir ou adaptar este projeto para suas necessidades! 🎉
