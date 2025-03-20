# **Apache JMeter™**

<div align="center">
  <img src="./images/logo.svg" alt="Apache JMeter logo">
</div>

**Apache JMeter™** é uma ferramenta de **código aberto** desenvolvida pela **Apache Software Foundation** para realizar **testes de performance**, **testes de carga** e **testes funcionais** em uma variedade de aplicações, com foco principal em **aplicações web**. Embora seja amplamente utilizada para testar o desempenho de sites e servidores web, o JMeter também é versátil o suficiente para testar outros serviços, como **bancos de dados**, **web services**, **mensageria** e até **aplicações móveis**.

### **Principais Funcionalidades do Apache JMeter:**

1. **Testes de Desempenho e Carga:**
   - O JMeter permite simular **carga** para testar como o sistema se comporta sob condições de estresse. Ele gera tráfego de usuários simultâneos para avaliar a capacidade de um sistema em lidar com grandes volumes de acesso.
   - Ele também possibilita a **medição do tempo de resposta** do sistema, oferecendo insights sobre a performance.

2. **Testes Funcionais:**
   - Embora seu foco principal seja performance, o JMeter também é eficiente em **testes funcionais**. Ele pode enviar requisições HTTP, testar APIs **RESTful** e **SOAP**, entre outros tipos de comunicação.

3. **Suporte a Diversos Protocolos:**
   - O JMeter é altamente configurável e oferece suporte a uma ampla gama de protocolos, como:
     - **HTTP/HTTPS** (para aplicações web)
     - **FTP** (para transferência de arquivos)
     - **JDBC** (para banco de dados)
     - **SMTP/POP3/IMAP** (para e-mail)
     - **SOAP e REST** (para web services)
     - **JMS** (para mensagens)
     - **TCP/UDP** (para protocolos personalizados)

4. **Geração de Relatórios e Análises:**
   - O JMeter oferece a geração de **relatórios detalhados**, gráficos e logs que ajudam a analisar o comportamento da aplicação durante os testes de carga.
   - As métricas podem incluir **tempo de resposta**, **throughput**, **taxa de erro**, entre outras.

5. **Execução Distribuída:**
   - Para realizar testes de larga escala, o JMeter pode ser configurado para ser executado em **múltiplas máquinas**, permitindo simular centenas ou até milhares de usuários simultâneos.

6. **Integração com CI/CD:**
   - O JMeter pode ser integrado a ferramentas de **Integração Contínua (CI)** e **Entrega Contínua (CD)**, como **Jenkins**, permitindo a execução automática de testes de carga a cada nova versão da aplicação.

7. **Interface Gráfica e Linha de Comando:**
   - O JMeter oferece uma interface gráfica (GUI) fácil de usar para configuração e execução de testes. Ele também possui um **modo de linha de comando**, útil para execução automatizada em ambientes de produção ou em pipelines de CI/CD.

### **Exemplos de Uso do JMeter:**

1. **Teste de Performance de Sites:**
   - Simule milhares de usuários simultâneos acessando um site e meça o tempo de resposta e o comportamento do servidor sob carga.

2. **Teste de APIs REST e SOAP:**
   - Envie múltiplas requisições HTTP (GET, POST, PUT, DELETE) para testar a performance e a robustez de APIs, avaliando como o servidor lida com diversas chamadas simultâneas.

3. **Teste de Banco de Dados (JDBC):**
   - Simule consultas a bancos de dados e meça a performance de transações SQL em um cenário de carga alta.

4. **Teste de Aplicativos Móveis:**
   - Teste a performance de APIs ou serviços consumidos por aplicativos móveis, simulando o comportamento de múltiplos usuários.

### **Vantagens do JMeter:**

- **Custo Zero:** Como é uma ferramenta de **código aberto**, o JMeter pode ser usado sem custos de licenciamento.
- **Extensibilidade:** O JMeter permite a criação de extensões e plugins personalizados, possibilitando a adição de novas funcionalidades ou a integração com outras ferramentas.
- **Facilidade de Uso:** Sua interface gráfica torna o JMeter acessível até para iniciantes em testes de performance.
- **Multiplataforma:** O JMeter é compatível com qualquer sistema operacional que suporte **Java** (Windows, Linux, macOS).
- **Relatórios Avançados:** A ferramenta gera **relatórios detalhados** com gráficos e métricas, facilitando a análise do desempenho da aplicação sob diferentes cenários de carga.

### **Comunidade e Suporte:**

- **Fórum e Discussões:** A comunidade do Apache JMeter é ativa e oferece suporte por meio de **fóruns e grupos de discussão**. Lá, usuários compartilham dicas, resolvem problemas e trocam scripts de teste.
- **Contribuições:** Como um projeto de código aberto, o JMeter aceita **contribuições**. Se você deseja ajudar a melhorar a ferramenta, consulte o [repositório do Apache JMeter no GitHub](https://github.com/apache/jmeter).

### **Conclusão:**

O **Apache JMeter™** é uma ferramenta robusta e poderosa para **testes de carga** e **desempenho**, amplamente utilizada por desenvolvedores e engenheiros de testes em todo o mundo. Com suas funcionalidades avançadas, como execução distribuída e geração de relatórios detalhados, o JMeter é ideal para avaliar a performance de sistemas sob grande carga e identificar gargalos que possam comprometer a experiência do usuário final.

---

### **Próximos Passos:**

- **[Instalação do JMeter](.docs/install.md):**  
  Guia passo a passo para instalar o **Apache JMeter** em diferentes sistemas operacionais (Windows, Linux, macOS).

- **[SERVEREST - API para Testes](https://serverest.dev/):**  
  API pública para testar carga e funcionalidades em um serviço RESTful. Ideal para validar a integração do JMeter com APIs.

- **[Criando o Primeiro Teste no JMeter](.docs/first-test.md):**  
  Aprenda a criar seu primeiro teste de carga, simulando requisições HTTP, configurando o ambiente e visualizando os resultados.

---

### **Links Úteis:**
- **Documentação oficial:** [Apache JMeter™ Documentation](https://jmeter.apache.org/)
- **Fórum de Discussão:** [JMeter User Mailing List](https://jmeter.apache.org/mail2.html)