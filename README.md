# App Química

TODO: Adicionar descrição e objetivo do projeto

## Requisitos:

- [Android Studio](https://developer.android.com/studio/install?hl=pt-br)
- Java SDK versão 17

## Tutorial sobre GIT

O Git é um controlador de versões de software, necessário para fazer a manutenção do projeto, no arquivo [TUTORIAL_GIT.md](TUTORIAL_GIT.md) tem o passo a passo de como configurar o git, criar branchs, fazer commits e pull requests.

## Instalação e Execução do Projeto:

**1 - Instalação via NVM**

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc

nvm install 20
nvm use 20
nvm alias default 20
```
**1.1 - verificar versões**
```bash
node -v
npm -v
```

- resultado deve ser algo como (pode variar alguns detalhes dependendo da máquina que está sendo utilizada):

```bash
v20.15.1
10.7.0
```

**2 - Java (JDK) versão 17**
  
  O Android realiza seu build com Java. A versão 17 é o padrão atual do React Native

```bash
sudo apt update
sudo apt install openjdk-17-jdk
```
**2.1 verificar versão**

```bash
java -version
```
- resultado deve ser algo como (pode variar alguns detalhes dependendo da máquina que está sendo utilizada):

```bash
openjdk version "17.0.18" 2026-01-20
OpenJDK Runtime Environment (build 17.0.18+8-Ubuntu-122.04.1)
OpenJDK 64-Bit Server VM (build 17.0.18+8-Ubuntu-122.04.1, mixed mode, sharing)
```

**3 - Android Studio**

O Download e a instalação do Android Studio pode demorar um pouco, o arquivo de instalação sugerido abaixo tem de 1,3GB.

```bash
cd ~
wget https://edgedl.me.gvt1.com/android/studio/ide-zips/2025.3.1.8/android-studio-panda1-patch1-linux.tar.gz

tar -xvzf android-studio-panda1-patch1-linux.tar.gz

sudo mv android-studio /opt/
```

**3.1 - Executar Android Studio**
  
```bash
/opt/android-studio/bin/studio.sh
```

**3.2 - Criar atalho do Android Studio (Opcional)**
  
```bash
sudo ln -s /opt/android-studio/bin/studio.sh /usr/local/bin/android-studio
```

**3.3 - Abrir Android Studio pelo terminal**
  
```bash
android-studio
```

Ao abrir o Android Studio pela primeira vez ele vai exibir uma janela solicitando a seleção do tipo de setup da IDE, escolha a Standard, é a utilizada no desenvolvimento desse projeto.

**4 - Configurar variáveis de ambiente**

Adicione no ~/.bashrc (padrão do terminal linux) ou ~/.zshrc:

Exemplo:
```bash
nano ~/.bashrc
```

```bash
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
```

**5 - Checklist dos componentes necessários**

Se tudo responder sem erro, seu ambiente está pronto.

```bash
adb version
emulator -list-avds
ls $ANDROID_HOME/platforms
ls $ANDROID_HOME/build-tools
```

**6 - Dependências Adicionais para o Linux**

Rode o comando abaixo para instalar as dependências que podem estar faltando na máquina.

```bash
sudo apt install -y \
  build-essential \
  libssl-dev \
  libffi-dev \
  python3 \
  python3-pip \
  git \
  curl \
  unzip
```

**7 - Configurar a aceleração de hardware para o Android Emulator**

O emulador vai ser melhor executado se puder usar o hardware da máquina, como a CPU, a GPU e o modem, em vez de ser executado como um software puro. A capacidade de usar o hardware da sua máquina para melhorar o desempenho é chamada de aceleração de hardware.

O emulador pode usar a aceleração de hardware para melhorar a experiência de duas maneiras principais:

Aceleração gráfica para melhorar a renderização de telas
Aceleração de máquina virtual (VM) para melhorar a velocidade de execução
A aceleração de hardware é ativada por padrão na maioria das máquinas. Se ela não está ativada na sua máquina, siga a descrição de [como configurar a aceleração de elementos gráficos e da máquina virtual (VM)](https://developer.android.com/studio/run/emulator-acceleration?utm_source=android-studio-app&utm_medium=app&hl=pt-br#vm-linux) para ter um desempenho melhor do emulador.

**8 - Configurar um dispositivo Android virtualmente para desenvolver o App**

1. Abra Device Manager
2. Clique em Create Device
3. Escolha um modelo
4. Configure o modelo conforme seus requsitos/preferências
5. Aperte o Botão [Finish/Finalizar]

**9 - Instalando Expo**

O Expo é uma ferramenta que simplifica o desenvolvimento com React Native, fornecendo APIs prontas e eliminando a necessidade de configuração inicial complexa do ambiente nativo.

```bash
npm install -g expo-cli
```
**9.1 Acessando e iniciando o app na máquina virtual (VM)**
```bash
cd AppQuimica
npm start
```
