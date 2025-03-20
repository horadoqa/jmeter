# **Instalação do Apache JMeter no Windows**

1. **Baixar o Apache JMeter**
   - Acesse a página oficial de downloads do JMeter: [https://jmeter.apache.org/download_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi).
   - Na seção "Binaries", baixe o arquivo no formato `.zip`.
   - Copie o arquivo compactado para a pasta C:\Arquivos de Programas

2. **Extrair o arquivo**
   - Na pasta `C:\Arquivos de Programas`, clique com o botão direito no arquivo `.zip` e selecione "Extrair tudo..." para descompactar o arquivo em um diretório de sua escolha.

3. **Configurar a variável JMETER_HOME**
   - Para garantir que o JMeter encontre o Java, configure a variável `JMETER_HOME`:
     1. Abra as **Configurações de Sistema Avançadas**.
     2. Clique em **Variáveis de Ambiente**.
     3. Em **Variáveis do Sistema**, clique em **Nova** e defina:
        - Nome: `JMETER_HOME`
        - Valor: O caminho onde o JMeter está instalado (exemplo: `C:\jmeter`).
     4. Configurar no Path: %JMETER_HOME% e %JMETER_HOME%\bin
     Clique em **OK** e reinicie o computador, se necessário.
     
     
4. **Instalar o Java**
   - O JMeter é uma aplicação Java, então você precisa ter o Java instalado no seu computador.
   - Baixe o Java JDK [aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ou use o OpenJDK.
   - Nome do arquivo: jdk-11.0.26_windows-x64_bin.exe
   - Vai pedir para fazer um cadastro

5. **Verifique se o Java já está instalado**
     - Abra o Prompt de Comando e digite:
     ```cmd
     java -version
     ```

6. **Iniciar o JMeter**
   - Acesso o Prompt de Comando e execute:
    ```bash
    JMeter
    ```

7. **Usar o JMeter Plugins Manager**

O JMeter possui um Plugin Manager que facilita a instalação e atualização de plugins.
Para instalar ou atualizar plugins, abra o JMeter, vá em Options > Plugins Manager, e veja as opções de plugins disponíveis ou atualizações.