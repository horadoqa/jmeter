# **Dockerfile:**

1. **Imagem Base:**  
   Utilizamos o Ubuntu 20.04 como imagem base.

2. **Instalação de Dependências:**
   - Instalamos o **OpenJDK 11** (necessário para rodar o JMeter).
   - Instalamos o **wget** (para baixar o JMeter) e **tar** (para extrair o arquivo baixado).
   
3. **Baixar e Instalar o JMeter:**
   - O comando `wget` baixa o arquivo **tgz** do Apache JMeter da URL oficial.
   - O comando `tar` descompacta o arquivo na pasta `/opt`.
   - Removemos o arquivo `.tgz` após a instalação para reduzir o tamanho da imagem.

4. **Definir Diretório de Trabalho:**  
   A imagem é configurada para o diretório `/opt/apache-jmeter-${JMETER_VERSION}`, onde o JMeter está instalado.

5. **Configuração do PATH:**  
   A variável de ambiente `PATH` é configurada para incluir o diretório `bin` do JMeter, permitindo que o comando `jmeter` seja executado a partir de qualquer local dentro do container.

6. **Expor Portas:**  
   Se for necessário acessar o JMeter via GUI ou para serviços relacionados, podemos expor as portas padrão para a interface gráfica (1099, 4445, 5050), embora o comando padrão do JMeter seja em modo não gráfico.

7. **Comando Padrão:**  
   O comando padrão executa o JMeter no modo não gráfico (`-n`), com um arquivo de teste JMeter (`test.jmx`). Você pode substituir `"test.jmx"` pelo seu próprio arquivo de teste ou usar o modo gráfico (`-gui`) se desejar.

---

### **Passos para Construir e Rodar a Imagem Docker:**

1. **Criar o arquivo `Dockerfile`:**

   Crie um arquivo chamado `Dockerfile` e cole o conteúdo acima nele.

2. **Construir a Imagem Docker:**

   No diretório onde o `Dockerfile` está localizado, execute o seguinte comando para construir a imagem:

   ```bash
   docker build -t jmeter-ubuntu .
   ```

3. **Rodar o Container:**

   Após a construção da imagem, você pode rodar um container baseado nela:

   ```bash
   docker run -it --rm jmeter-ubuntu
   ```

   Caso você queira executar um **teste específico** com o JMeter (por exemplo, um arquivo `.jmx` local), você pode montar um volume com o arquivo de teste e executá-lo:

   ```bash
   docker run -it --rm -v /caminho/para/seu/teste.jmx:/teste.jmx jmeter-ubuntu -n -t /teste.jmx
   ```

---

### **Conclusão:**

Agora, você tem uma imagem Docker personalizada com o **JMeter** instalado em **Ubuntu**! Esse container pode ser utilizado para executar testes de desempenho sem a necessidade de instalação local do JMeter, facilitando o uso em diferentes ambientes e máquinas.
