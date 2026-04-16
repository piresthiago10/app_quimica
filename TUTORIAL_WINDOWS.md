# Instalação e Execução do Projeto NO Windows:

## Requisitos:

- [Android Studio](https://developer.android.com/studio/install?hl=pt-br)
- Java SDK versão 17
- NVM versão 0.39.7
- Node versão 24
- Npm versão 11
- Expo versão 55.0.15
- [Git](https://git-scm.com/)


**1 - Instalação via NVM**

```bash
# Baixar e instalar o Chocolatey:
powershell -c "irm https://community.chocolatey.org/install.ps1|iex"

# Baixar e instalar o Node.js:
choco install nodejs --version="24.15.0"

# Verifique a versão do Node.js:
node -v # Deve exibir "v24.15.0".

# Verificar a versão do npm:
npm -v # Deve imprimir "11.12.1".
```

**1.1 - verificar versões**
```bash
node -v
npm -v
```

- resultado deve ser algo como (pode variar alguns detalhes dependendo da máquina que está sendo utilizada):

```bash
v24.15.0
11.12.1
```

**2 - Instalando Expo**

O Expo é uma ferramenta que simplifica o desenvolvimento com React Native, fornecendo APIs prontas e eliminando a necessidade de configuração inicial complexa do ambiente nativo.

```bash
npm install -g expo-cli
```
**2.1 Acessando e iniciando o app na máquina virtual (VM)**
```bash
cd <caminho-do-projeto>/AppQuimica
npx expo start
```

**2 - Android Studio**

O Download e a instalação do Android Studio pode demorar um pouco, o arquivo de instalação sugerido abaixo tem de 1,3GB.

Acesse esse o link de download do [Android Studio](https://edgedl.me.gvt1.com/android/studio/install/2025.3.3.7/android-studio-panda3-patch1-windows.exe).

Ao abrir o Android Studio pela primeira vez ele vai exibir uma janela solicitando a seleção do tipo de setup da IDE, escolha a Standard, é a utilizada no desenvolvimento desse projeto.

**3 - Configurar variáveis de ambiente (CRÍTICO)**

No Windows:

Abra:
```
Painel de Controle → Sistema → Variáveis de Ambiente
```
Crie:

ANDROID_HOME
```
C:\Users\SEU_USUARIO\AppData\Local\Android\Sdk
```
PATH (adicione):
```
%ANDROID_HOME%\emulator
%ANDROID_HOME%\platform-tools
%ANDROID_HOME%\tools
%ANDROID_HOME%\tools\bin
```

**4 - Criar e iniciar um emulador Android**

Abra o Android Studio

Vá em:
```
More Actions → Virtual Device Manager
```
Clique em:
```
Create Device
```
- Escolha um dispositivo (ex: Pixel 5)
- Baixe uma imagem (recomendo API 33 ou 34)
- Finalize e clique em ▶ para iniciar