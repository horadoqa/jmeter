# Instalação

Para instalar o **Apache JMeter**, siga as etapas abaixo:

### 1. **Baixar o Apache JMeter**
   - Acesse a página oficial de downloads do JMeter: [https://jmeter.apache.org/download_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi).
   - Na seção "Binaries", escolha o arquivo no formato `.tgz` ou `.zip` dependendo do seu sistema operacional.

### 2. **Extrair o arquivo**
   - Após o download, extraia o arquivo compactado em um diretório de sua escolha.
     - No Windows, clique com o botão direito no arquivo `.zip` e selecione "Extrair tudo...".
     - No Linux, você pode usar o comando:
     ```bash
     tar -xvzf apache-jmeter-X.X.tgz
     ```
     (substitua `X.X` pela versão específica).

### 3. **Instalar o Java**
   O JMeter é uma aplicação Java, então você precisa ter o Java instalado no seu computador.

   - **Verificar se o Java está instalado:**
     Abra o terminal ou prompt de comando e digite:
     ```
     java -version
     ```
     Se o Java estiver instalado, ele mostrará a versão. Caso contrário, instale o Java:
     - **Windows**: Baixe o Java JDK [aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ou use o OpenJDK.
     - **Linux**: Use o comando adequado para sua distribuição, como:
       - Para **Ubuntu/Debian**: `sudo apt install openjdk-11-jdk`
       - Para **CentOS/RHEL**: `sudo yum install java-11-openjdk-devel`

### 4. **Configurar a variável JAVA_HOME (se necessário)**
   Para garantir que o JMeter encontre o Java, configure a variável `JAVA_HOME`.

   - **No Windows**:
     1. Abra as **Configurações de Sistema Avançadas**.
     2. Clique em **Variáveis de Ambiente**.
     3. Em **Variáveis do Sistema**, clique em **Nova** e defina:
        - Nome: `JAVA_HOME`
        - Valor: O caminho onde o Java está instalado (por exemplo, `C:\Program Files\Java\jdk-11.0.10`).
     4. Clique em **OK** e reinicie o computador, se necessário.

   - **No Linux**:
     Adicione a seguinte linha no seu arquivo `~/.bashrc` ou `~/.zshrc`:
     ```
     export JAVA_HOME=/caminho/para/o/java
     export PATH=$JAVA_HOME/bin:$PATH
     ```
     Substitua `/caminho/para/o/java` pelo caminho correto. Depois, execute:
     ```
     source ~/.bashrc
     ```

### 5. **Iniciar o JMeter**
   - **Windows**: No diretório onde você extraiu o JMeter, execute o arquivo `jmeter.bat` (clicando duas vezes).
   - **Linux/macOS**: No terminal, navegue até o diretório do JMeter e execute o comando:
     ```
     ./bin/jmeter
     ```

Agora, o Apache JMeter deve abrir e você pode começar a configurar e rodar seus testes de performance.

Se você tiver algum problema ou dúvida durante o processo, me avise e eu posso te ajudar!