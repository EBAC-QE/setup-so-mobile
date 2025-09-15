# 🚀 Guia de Instalação – Appium + WebdriverIO + Android Studio (Windows)

## 1. Instalar JDK
- Baixe o [Temurin JDK 17](https://adoptium.net/) (ou versão LTS).
- Instale em `C:\Program Files\Java\jdk-17`.

### Variáveis de ambiente
- Crie a variável `JAVA_HOME` → `C:\Program Files\Java\jdk-17`
- Edite o `PATH` e adicione:
  ```
  %JAVA_HOME%\bin
  ```

Verifique:
```bash
java -version
echo %JAVA_HOME%
```

---

## 2. Instalar Node.js e npm
- Baixe de [nodejs.org](https://nodejs.org/) a versão **LTS**.
- Durante a instalação, marque “Add to PATH”.

Verifique:
```bash
node -v
npm -v
```

---

## 3. Instalar Android Studio
- Baixe de [developer.android.com/studio](https://developer.android.com/studio).
- Abra **SDK Manager** e instale:
  - SDK Platform (Android 13 ou 14)
  - Android SDK Platform-tools
  - Android SDK Build-tools
  - Android Emulator
  - Command-line Tools (latest)

### Variáveis de ambiente
- Crie `ANDROID_HOME`:
  ```
  C:\Users\<SEU_USUARIO>\AppData\Local\Android\Sdk
  ```
- Edite `PATH` e adicione:
  ```
  %ANDROID_HOME%\platform-tools
  %ANDROID_HOME%\emulator
  %ANDROID_HOME%\cmdline-tools\latest\bin
  ```

Verifique:
```bash
adb version
sdkmanager --list
```

---

## 4. Ativar Hypervisor
- Abra **BIOS/UEFI** → ative **Intel Virtualization (VT-x)**.
- No Windows, habilite **Hyper-V** ou **Intel HAXM**:
  ```powershell
  dism.exe /Online /Enable-Feature:Microsoft-Hyper-V /All
  ```

---

## 5. Instalar Appium
```bash
npm install -g appium
```

Verifique:
```bash
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
- Baixe em: [Appium Inspector Releases](https://github.com/appium/appium-inspector/releases).
- Instale e abra → use para inspecionar elementos.

---

## 8. Baixar app de teste (WebdriverIO Demo App)
- Baixe o APK em:
  [wdio-demo-app releases](https://github.com/webdriverio/native-demo-app/releases)
- Exemplo: `android.wdio.native.app.v1.0.8.apk`

---

## 9. Verificações rápidas
```bash
adb devices
```
✅ deve listar seu emulador ou celular.

```bash
emulator -list-avds
```
✅ lista os emuladores disponíveis.

```bash
appium
```
✅ inicia o servidor Appium.

---

## 📌 Recomendações
- Use pelo menos **16 GB RAM** para rodar emuladores.
- Prefira `appPackage`/`appActivity` para não reinstalar APK sempre.
- Configure timeouts mais altos no WebdriverIO (apps são mais lentos que web).
