# Crypto Monitor

Aplicativo Android desenvolvido em Kotlin durante as aulas de programação mobile. O objetivo principal do projeto é fornecer ao usuário a cotação atual do Bitcoin em tempo real, utilizando uma requisição a uma API pública de criptomoedas.

## 🧭 Como Funciona?

Ao abrir o aplicativo, o usuário verá uma interface com a imagem de um Bitcoin e um botão para **"Atualizar"**. Ao clicar neste botão, o app faz uma requisição à API do Mercado Bitcoin para obter o valor atual da criptomoeda e exibe a cotação na tela.

### 📱 Tela Inicial

![imagem de inicialização](https://github.com/bailooon/Crypto-Monitor/blob/master/images/CryptoMonitorIniciar.png)

### 🔄 Após Clicar em "Atualizar"

![imagem após a ação](https://github.com/bailooon/Crypto-Monitor/blob/master/images/CryptoMonitorAcao.png)

---

## 🛠️ Estrutura do Projeto

### `MainActivity.kt`
Controla a interface principal da aplicação. A `MainActivity` configura a toolbar, trata o clique do botão "Atualizar" e faz a chamada para a API utilizando corrotinas. Quando a resposta é recebida, a cotação do Bitcoin e a data/hora da última atualização são formatadas e exibidas na tela. A classe também realiza o tratamento de erros para garantir que o usuário seja informado em caso de falha na requisição.

### `MercadoBitcoinService.kt`
Interface do Retrofit responsável por definir o endpoint da API que retorna a cotação do Bitcoin.

### `MercadoBitcoinServiceFactory.kt`

Classe responsável por criar e configurar a instância do Retrofit. Ela define a base URL da API e utiliza o conversor GsonConverterFactory para lidar com a conversão dos dados JSON da resposta da API para objetos Kotlin:

### `activity_main.xml`

Layout principal da aplicação. Ele usa o recurso `<include>` para modularizar a interface e separar a lógica da tela em componentes reutilizáveis:

- `component_toolbar_main.xml`
- `component_quote_information.xml`
- `component_button_refresh.xml`

