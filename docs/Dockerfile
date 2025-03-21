# Etapa 1: Usar uma imagem base do Ubuntu
FROM ubuntu:20.04

# Evitar interação durante a instalação (para que a instalação não bloqueie o processo)
ENV DEBIAN_FRONTEND=noninteractive

# Etapa 2: Instalar dependências básicas e Java
RUN apt-get update && apt-get install -y \
    openjdk-11-jdk \
    wget \
    tar \
    && apt-get clean

# Etapa 3: Definir a versão do JMeter que será instalada
ENV JMETER_VERSION 5.4.1

# Etapa 4: Baixar e instalar o Apache JMeter
RUN wget https://dlcdn.apache.org/jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz -P /tmp && \
    tar -xvzf /tmp/apache-jmeter-${JMETER_VERSION}.tgz -C /opt && \
    rm /tmp/apache-jmeter-${JMETER_VERSION}.tgz

# Etapa 5: Definir o diretório de trabalho para o JMeter
WORKDIR /opt/apache-jmeter-${JMETER_VERSION}

# Etapa 6: Definir a variável de ambiente para o JMeter
ENV PATH="${PATH}:/opt/apache-jmeter-${JMETER_VERSION}/bin"

# Etapa 7: Expor a porta para acesso ao JMeter GUI (se necessário)
EXPOSE 1099 4445 5050

# Etapa 8: Comando padrão para rodar o JMeter em modo não gráfico
CMD ["jmeter", "-n", "-t", "test.jmx"]
