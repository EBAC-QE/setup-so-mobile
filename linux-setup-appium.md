# 🚀 Guia de Instalação – Appium + WebdriverIO + Android Studio (Linux)

## 1. Instalar Node.js e npm
```bash
sudo apt update
sudo apt install -y nodejs npm
```
ou use **nvm** para gerenciar versões.  

Verifique:
```bash
node -v
npm -v
```

---

## 2. Instalar JDK
```bash
sudo apt install openjdk-21-jdk
```

Adicione ao `~/.bashrc`:
```bash
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
```

Recarregue:
```bash
source ~/.bashrc
```

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
Adicione ao `~/.bashrc`:
```bash
export ANDROID_HOME=$HOME/Android/Sdk
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
- Ative **Intel VT-x** ou **AMD-V** na BIOS.  
- Instale KVM:
```bash
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils
```

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
- Dê permissão de execução:
```bash
chmod +x Appium-Inspector.AppImage
./Appium-Inspector.AppImage
```

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
- Ter pelo menos **16 GB RAM**.  
- Instalar pacotes de 32 bits:
```bash
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install libc6:i386 libstdc++6:i386
```
- Configurar regras `udev` para dispositivos físicos.
