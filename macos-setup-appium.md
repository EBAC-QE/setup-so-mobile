# 🚀 Guia de Instalação – Appium + WebdriverIO + Android Studio (macOS)

## 1. Instalar Node.js e npm

Baixe de: https://nodejs.org/en/download

Para saber o seu tipo de processador, via terminal rode:  `uname -m`
Se aparecer x86_64 é intel 
Se aparecer arm64 é apple Silicon (M1, M2, M3, etc.)

Ou instale via Homebrew: 
```bash
brew install node
```
Instale o homebrew caso não tenha: https://brew.sh/

Verifique:
```bash
node -v
npm -v
```

---


## 2. Instalar JDK

Baixe de: https://www.oracle.com/java/technologies/downloads

```bash
brew install openjdk@17
```

Adicione ao ~/.zshrc: `nano ~/.zshrc`
```bash
export JAVA_HOME=$(/usr/libexec/java_home -v 21)
export PATH=$JAVA_HOME/bin:$PATH
```

Salve e confirme:
ctrl + o
Enter
ctrl + x

Recarregue o arquivo: `source ~/.zshrc`

Verifique:
```bash
java -version
echo $JAVA_HOME
```

---

## 3. Instalar Android Studio
- Baixe em [developer.android.com/studio](https://developer.android.com/studio).
- No **SDK Manager**, instale:
  - SDK Platform (Android 13 ou 14)
  - Android SDK Platform-tools
  - Android SDK Build-tools
  - Android Emulator
  - Command-line Tools (latest)

### Variáveis de ambiente
Adicione ao ~/.zshrc: `nano ~/.zshrc`
```bash
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$ANDROID_HOME/platform-tools:$PATH
export PATH=$ANDROID_HOME/emulator:$PATH
export PATH=$ANDROID_HOME/cmdline-tools/latest/bin:$PATH
```

Salve e confirme:
ctrl + o
Enter
ctrl + x

Recarregue o arquivo: `source ~/.zshrc`

Verifique:
```bash
adb version
```
Verifique a lista de emuladores:
```bash
adb devices
emulator -list-avds
```
Execute o emulador via comando:
```bash
emulator -avd <nome_emulador>
Ex.
emulator -avd Pixel_8
```

---

## 4. Virtualização
- Em Macs Intel: usar **HAXM** (já incluído no Android Studio).
- Em Apple Silicon (M1/M2/M3): usar imagens **ARM64** no AVD.

---

## 5. Instalar Appium
```bash
npm install -g appium
```

Caso dê erro de permisão, tente como admim: 
```bash
sudo npm install -g appium
```

Instalar driver UiAutomator2:
```bash
appium driver install uiautomator2
```

Caso dê erro de permisão, tente como admim: 
```bash
sudo appium driver install uiautomator2
```
Verificar drivers instalados: 
```bash
appium driver list
```


```bash
appium -v
```

Executar o appium: 
```bash
appium
```
---

## 6. Validar com Appium Doctor
```bash
npm install appium-doctor -g
ou
sudo npm install appium-doctor -g
appium-doctor --android
```

---

## 7. Instalar Appium Inspector
- Baixe em [Appium Inspector Releases](https://github.com/appium/appium-inspector/releases).
- Arraste para a pasta **Applications**.

---

## 8. Baixar app de teste (WebdriverIO Demo App)
- Baixe o APK:  
  [wdio-demo-app releases](https://github.com/webdriverio/native-demo-app/releases)

---

## 9. Exemplo de capabilities para o appium inspector 
{
  "platformName": "Android", 
  "appium:deviceName": "Medium Phone",
  "appium:platformVersion": "9.0",
  "appium:app": "/Users/prof/Desktop/App/wdio.apk",
  "appium:automationName": "UiAutomator2"
}

Sendo: 
- Android, nome do sistema operacional
- Medium Phone, nome do emulador configurado
- 9.0 a versão do emulador confgurado
- /Users/meu_usuário/Desktop/App/wdio.apk, o caminho do emulador, considerando trocar o nome do usuário ( meu_usuário ) e o nome do arquivo .apk
- UiAutomator2 o driver do appium 


## 📌 Recomendações
- Prefira Macs com **16 GB RAM** para rodar emuladores.  
- Não precisa instalar drivers USB extras (mac já reconhece Android).  
- Se usar M1/M2/M3, escolha imagens ARM64 para emuladores.
