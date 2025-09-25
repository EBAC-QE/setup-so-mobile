# 📱 Setup Mobile Automation - Appium + WebdriverIO

Este repositório contém guias completos de instalação e configuração para **automação de testes mobile** usando **Appium** e **WebdriverIO** em diferentes sistemas operacionais.

## 🎯 Objetivo

Fornecer guias passo a passo para configurar um ambiente completo de automação mobile, incluindo:
- ✅ Node.js e npm
- ✅ Java Development Kit (JDK)
- ✅ Android Studio e SDK
- ✅ Appium Server
- ✅ Appium Inspector
- ✅ Configuração de emuladores Android
- ✅ Validação do ambiente

## 📋 Guias por Sistema Operacional

Escolha o guia correspondente ao seu sistema operacional:

### 🐧 [Linux](linux-setup-appium.md)
Guia completo para configuração em distribuições baseadas em Ubuntu/Debian.
- Instalação via `apt` e `npm`
- Configuração de KVM para virtualização
- Variáveis de ambiente no `.bashrc`
- Pacotes de 32 bits para compatibilidade

### 🍎 [macOS](macos-setup-appium.md)
Guia otimizado para Mac Intel e Apple Silicon (M1/M2/M3).
- Instalação via Homebrew
- Configuração específica para diferentes processadores
- Variáveis de ambiente no `.zshrc`
- Emuladores ARM64 para Apple Silicon

### 🪟 [Windows](windows-setup-appium.md)
Guia para Windows 10/11 com PowerShell.
- Instalação via executáveis
- Configuração de variáveis de ambiente via GUI
- Habilitação de Hyper-V/Intel HAXM
- Resolução de problemas comuns

## 🛠️ Ferramentas Incluídas

| Ferramenta | Versão Recomendada | Descrição |
|------------|-------------------|-----------|
| **Node.js** | LTS (v18+) | Runtime JavaScript para Appium |
| **Java JDK** | 17 ou 21 | Necessário para Android SDK |
| **Android Studio** | Latest | IDE e ferramentas de desenvolvimento |
| **Appium** | 2.x | Servidor de automação mobile |
| **Appium Inspector** | Latest | Interface para inspecionar elementos |

## 📦 App de Teste

Todos os guias incluem o download do **WebdriverIO Demo App**:
- 📥 [Releases do wdio-demo-app](https://github.com/webdriverio/native-demo-app/releases)
- Aplicativo pronto para testes de automação
- Inclui diversos elementos para prática

## 🔧 Validação do Ambiente

Após seguir qualquer guia, você deve conseguir executar:

```bash
# Verificar instalações
node -v
java -version
adb version
appium -v

# Verificar dispositivos
adb devices
emulator -list-avds

# Validar configuração completa
appium-doctor --android
```

## 📋 Requisitos Mínimos

### Hardware
- **RAM**: 16 GB (recomendado para emuladores)
- **Storage**: 50 GB livres
- **Processador**: Suporte à virtualização (Intel VT-x / AMD-V)

### Software
- Sistema operacional atualizado
- Conexão à internet para downloads
- Acesso administrativo para instalações

## 🎯 Capabilities de Exemplo

Configuração básica para o Appium Inspector:

```json
{
  "platformName": "Android",
  "appium:deviceName": "Medium Phone",
  "appium:platformVersion": "13.0",
  "appium:app": "/caminho/para/seu/app.apk",
  "appium:automationName": "UiAutomator2"
}
```

## 🚨 Problemas Comuns

### ❌ Comando não encontrado
- Verifique se as variáveis de ambiente estão configuradas
- Reinicie o terminal após configuração
- Execute `source ~/.bashrc` (Linux) ou `source ~/.zshrc` (macOS)

### ❌ Emulador não inicia
- Verifique se a virtualização está habilitada na BIOS
- Instale HAXM (Intel) ou configure Hyper-V (Windows)
- Use imagens ARM64 em Apple Silicon

### ❌ Appium não conecta
- Verifique se o dispositivo/emulador está listado em `adb devices`
- Confirme se o Appium está rodando na porta correta (4723)
- Valide as capabilities no Inspector

## 🔗 Links Úteis

- [Documentação oficial do Appium](https://appium.io/docs/en/2.0/)
- [WebdriverIO para Mobile](https://webdriver.io/docs/api/appium)
- [Android Developer - Studio](https://developer.android.com/studio)
- [Appium Inspector](https://github.com/appium/appium-inspector)

## 🤝 Contribuição

Sinta-se à vontade para:
- Reportar problemas via Issues
- Sugerir melhorias
- Adicionar guias para outros sistemas
- Compartilhar dicas e soluções

## 📝 Licença

Este projeto é disponibilizado sob a licença MIT. Sinta-se livre para usar e modificar conforme necessário.

---

**💡 Dica**: Siga o guia específico do seu sistema operacional e execute todos os comandos de verificação para garantir que o ambiente está funcionando corretamente antes de começar a desenvolver seus testes!
