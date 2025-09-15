# 🚀 Guia de Instalação – Appium + WebdriverIO + Android Studio (macOS)

## 1. Instalar JDK
```bash
brew install openjdk@17
```

Adicionar ao `~/.zshrc`:
```bash
export JAVA_HOME=$(/usr/libexec/java_home -v 17)
export PATH=$JAVA_HOME/bin:$PATH
```

Verifique:
```bash
java -version
```

---

## 2. Instalar Node.js e npm
```bash
brew install node
```

Verifique:
```bash
node -v
npm -v
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
Adicione ao `~/.zshrc`:
```bash
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$ANDROID_HOME/platform-tools:$PATH
export PATH=$ANDROID_HOME/emulator:$PATH
export PATH=$ANDROID_HOME/cmdline-tools/latest/bin:$PATH
```

Verifique:
```bash
adb version
sdkmanager --list
```

---

## 4. Virtualização
- Em Macs Intel: usar **HAXM** (já incluído no Android Studio).
- Em Apple Silicon (M1/M2/M3): usar imagens **ARM64** no AVD.

---

## 5. Instalar Appium
```bash
npm install -g appium
appium -v
```

Instalar driver UiAutomator2:
```bash
appium driver install uiautomator2
```

---

## 6. Validar com Appium Doctor
```bash
npm install -g @appium/doctor
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

## 9. Verificações rápidas
```bash
adb devices
emulator -list-avds
appium
```

---

## 📌 Recomendações
- Prefira Macs com **16 GB RAM** para rodar emuladores.  
- Não precisa instalar drivers USB extras (mac já reconhece Android).  
- Se usar M1/M2/M3, escolha imagens ARM64 para emuladores.
