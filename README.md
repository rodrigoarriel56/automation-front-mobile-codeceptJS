<img width="313" height="163" alt="image" src="https://github.com/user-attachments/assets/2b2cdd59-8f15-47ef-981d-ed786707d543" />

### Automação de testes mobile com CodeceptJS
A automação de testes mobile com CodeceptJS e Appium permite criar testes end-to-end robustos, 
usando uma sintaxe em linguagem natural focada no comportamento do usuário (objeto I).
Essa camada abstrai a complexidade do driver, suportando aplicativos nativos e híbridos para Android e iOS

#### Requisitos e Instalação:
Certifique-se de ter o Node.js instalado e configure o ambiente: 
Instale o Appium globalmente via terminal: npm install -g appium.
Instale o driver do Appium desejado (ex: appium driver install uiautomator2 para Android).
No seu projeto de testes, instale o CodeceptJS e o WebDriver/Appium
```bash
bashnpm init -y
```
```bash
npm install codeceptjs webdriverio appium --save-dev
```

## Configuração do ambiente
Inicialize a configuração rodando npx codeceptjs init e selecione o helper Appium.
```bash
npx codeceptjs init
```

## Ajuste o arquivo codecept.conf.js
```bash
javascriptexports.config = {
  tests: './*_test.js',
  output: './output',
  helpers: {
    Appium: {
      app: '/caminho/para/seu/app.apk',
      platform: 'Android',
      device: 'emulator-5545', // ou o ID do dispositivo físico
      host: 'localhost',
      port: 4723,
      desiredCapabilities: {
        automationName: 'UiAutomator2'
      }
    }
  },
  include: {
    I: './steps_file.js'
  },
  name: 'projeto-teste-mobile'
};
```
## Use o código com cuidado.

## Appium-doctor
Verifica se todas as dependências do Appium são atendidas e se todas as dependências estão configuradas corretamente.
Para instalar o appium-doctor basta colar no seu terminal:
```bash
npm install -g appium-doctor  # instalar o appium-doctor
```
Uma vez que o node.js, npm e o appium-doctor estão instalados, você pode usar o comando abaixo para verificar se todas as dependências do appium são atendidas:

```bash
appium-doctor             # verificar todas as dependencias necessárias para usar o appium
appium-doctor --android   # verificar as dependências somente para android
appium-doctor --ios       # verificar as dependências somente para ios
```
## Agora vamos ao Projeto de Fato:
## Rodar o Sh com as Dependencias:

Acessar o diretório por terminal e rodar o seguinte comando:
```bash
$ sh install_dependencies.sh
```

## Configurar seu Bash Profile:
Adicionar isso no seu sudo:
```bash
vi ~/.bash_profile
```
```bash
export ANDROID_HOME=/Users/$(whoami)/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH/:$ANDROID_HOME/platform-tools
export JAVA_HOME=$(/usr/libexec/java_home)
#export PATH=${JAVA_HOME}/bin:$PATH
```

## Rodar o comando para salvar o bash profile:
Run: 
```bash
sudo vi ~/.bash_profile
```
Se rodar o appium-doctor e aparecer problema no bin, por favor descomentar a ultima linha do bin e rodar o comando do passo 3 novamente.

## O CodeceptJS deve ser instalado com suporte ao webdriverio:
```bash
npm install codeceptjs webdriverio --save
```
ou 
```bash
npm install webdriverio
```

## Json para configurar o Appium Desktop:
Android:
{
  "platformName": "Android",
  "deviceName": "920110594119334a",
  "app": "C:\\GitMobile\\FrameworkMobile\\automationMobile\\App\\Android\\app-qa-release0.64.0.apk",
  "automationName": "uiautomator2"
}

IOS:
 {
  "app": "C:\\GitMobile\\FrameworkMobile\\automationMobile\\App\\iOS\\.ipa"",
  "platformName": "iOS",
  "platformVersion": "12.2",
  "deviceName": "iPhone X"
}

## Execução dos testes
Inicie o servidor Appium, digitando appium no terminal.
Abra o seu emulador ou conecte o dispositivo.
Execute os testes:
```bash
npx codeceptjs run
```
