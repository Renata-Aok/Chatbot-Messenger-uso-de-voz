Uso de voz com Watson Speech to Text e Text to Speech em ChatBot Watson Assistant integrado ao Facebook Messenger

Programação por fluxo: Node-RED

URL do Aplicativo: https://node-red-rrcl.mybluemix.net 

Origem: https://us-south.git.cloud.ibm.com/renata.aok/NodeREDRRCL

Etapas da Aplicação

- Criação ChatBot simples com Watson Assistant - Reserva de mesa;
 
Credenciais da skill
Skill details
Skill name:Reserva mesa
Skill ID:8775d1c5-8dcd-4cd9-9207-a8f3348268f7
Legacy v1 workspace URL:https://api.us-south.assistant.watson.cloud.ibm.com/instances/4d04144e-5b0a-4b5f-89b7-c42ad3a7ea03/v1/workspaces/8775d1c5-8dcd-4cd9-9207-a8f3348268f7/message
Service credentials
Service credentials name:fe0d33d3-4ed9-4737-a09d-32459dfcd082
API key:J4QK1x185lAAYT3Dv-XC1FhEyKIVXHefsP266meUK-EY
Service credentials name:auto-generated-apikey-b3b28e11-c15c-4169-b1cd-85c11b60f495
API key:8v_C_CzKsL1z_ulFz_UALdf9cKbycE7iahD2D0CKA1fi
Service credentials name:Auto-generated service credentials

- Além do Watson Assistant foram criados mais dois serviços no IBM Cloud: Watson Speech to Text e  Text to Speech;
 
Watson Speech to Text
API key:
fIcuBGHhzoiKNZ85aFgO4ySO6XIu7bjJpOaQ390jU49T

Watson Text to Speech;
API key:
REX3RlTUux4tRAf07fRll8BN7cqURFmCfgwT7JmIaNs1

- Configurado ambiente para orquestração das API’s por Node-Red no IBM Cloud. O ambiente proporciona ferramenta de desenvolvimento completa para orquestração de fluxos.
Link do ambiente de desenvolvimento criado: https://node-red-rrcl.mybluemix.net/red/#flow/bcba5651.986b58

- Implementação de fluxo para conversação;

O fluxo recebe um link do messenger, converte para formato WAV, envia para o Speech to text para transcrição e envia a transcrição para o Watson Assistant. Com a resposta do Watson Assistant, o Text to Speech para converte em áudio, converte para MP3 (formato usado pelo Facebook Messenger), armazenar em uma sessão de variável global e enviar de volta um link para o Facebook Messenger. Esse fluxo usa o nó ffmpeg para converter áudio. Esse fluxo recebe o nome e o sobrenome do facebook e é enviado ao contexto dentro do WA.

Arquivo Json do Fluxo, em anexo

- Criação de página no Facebook : Bot Reservas
- Teste de resposta do Chat antes de contectar ao Facebook Messenger
-  Integração com o Chatfuel que conectará o fluxo do orquestrador ao Facebook Messenger



 ###### O bot simples é para reserva de mesa em um restaurante genérico.
Sugestões de perguntas ao Bot:

- Saudações: bom dia, boa tarde, boa noite, olá, oi, como vai?
- Gostaria de uma reserva, Faça uma reserva, Preciso de mesa para dois, preciso de uma mesa
- Onde vocês ficam? Fica onde? Qual endereço?
- Despedida: tchau, até logo, fui, tchau, tô indo, valeu
- Cancelar: desisti, esqueçe, cancela, não quero mais, depois falo com você


Link para conversação com o bot em dispositivo mobile:
https://m.me/botreservas.com.br?fbclid=IwAR3eaz15vYKrGpUFhiNhs2nddJhQIX3CNpt51jpURmbD7jarnmU3u34nRlQ
