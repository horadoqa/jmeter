# **Instalação do Apache JMeter no Linux**

1. **Baixar o Apache JMeter**
   - Acesse a página oficial de downloads do JMeter: [https://jmeter.apache.org/download_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi).
   - Na seção "Binaries", baixe o arquivo no formato `.tgz`.

2. **Extrair o arquivo**
   - Após o download, use o comando abaixo no terminal para descompactar o arquivo:
     ```bash
     tar -xvzf apache-jmeter-X.X.tgz
     ```
     (substitua `X.X` pela versão específica do JMeter).

3. **Instalar o Java**
   - O JMeter requer Java. 
   - Caso o Java não esteja instalado, instale o OpenJDK:
     - Para **Ubuntu/Debian**:
       ```bash
       sudo apt install openjdk-11-jdk
       ```
     - Para **CentOS/RHEL**:
       ```bash
       sudo yum install java-11-openjdk-devel
       ```
   
   Verifique a versão do JAVA:
     ```bash
     java -version
     ```
    
    O resultado será:
    ```bash
    java -version
    openjdk version "11.0.26" 2025-01-21
    OpenJDK Runtime Environment (build 11.0.26+4-post-Ubuntu-1ubuntu122.04)
    OpenJDK 64-Bit Server VM (build 11.0.26+4-post-Ubuntu-1ubuntu122.04, mixed mode, sharing)
    ```
### 4. **Configurar a variável JAVA_HOME**

Para garantir que o JMeter encontre o Java, adicione a seguinte linha no seu arquivo `~/.bashrc` ou `~/.zshrc`:

1. **Localize o caminho do JMeter**: 
    Use o comando `which jmeter` para encontrar o caminho correto do Java instalado no seu sistema:

    ```bash
    which jmeter
    ```
    
    Isso deve retornar algo como `/usr/bin/java` ou outro caminho, dependendo de onde o Java está instalado. Para continuar, você precisará do caminho da instalação do Java, não do caminho do executável em si.

2. **Obtenha o diretório do Java**: O caminho retornado pelo comando `which java` será um link simbólico para o executável Java. Para descobrir o diretório completo, você pode usar o comando `readlink`:

    ```bash
    readlink -f $(which java)
    ```

    Isso retornará o caminho completo, algo como `/usr/lib/jvm/java-11-openjdk-amd64/bin/java`.

3. **Defina a variável JAVA_HOME**: Com o caminho completo, edite o arquivo `~/.bashrc` ou `~/.zshrc` (dependendo de qual shell você usa) e adicione as seguintes linhas:

    ```bash
    export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
    export PATH=$JAVA_HOME/bin:$PATH
    ```

    **Substitua** o caminho `/usr/lib/jvm/java-11-openjdk-amd64` pelo caminho real do Java que você obteve com o comando `readlink`.

4. **Carregar as alterações**: Após editar o arquivo, carregue as alterações executando o comando:

    ```bash
    source ~/.bashrc
    ```

    Ou, se você usa o `zsh`, execute:

    ```bash
    source ~/.zshrc
    ```

Agora, a variável `JAVA_HOME` deve estar corretamente configurada, e o JMeter será capaz de localizar o Java. Você pode verificar se a configuração foi bem-sucedida executando:

```bash
echo $JAVA_HOME
```

Isso deve retornar o caminho correto para o diretório do Java.

5. **Iniciar o JMeter**
   - No terminal, navegue até o diretório do JMeter e execute o comando:
     ```bash
     ./bin/jmeter
     ```