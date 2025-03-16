# Criar teste

Para criar o seu primeiro teste no **Apache JMeter**, siga estas etapas:

### 1. **Abrir o JMeter**
   - Inicie o JMeter conforme mencionado anteriormente:
     - **Windows**: Execute o arquivo `jmeter.bat` na pasta onde o JMeter foi extraído.
     - **Linux/macOS**: No terminal, navegue até o diretório onde o JMeter foi extraído e execute o comando:
       ```
       ./bin/jmeter
       ```

### 2. **Criar um Novo Plano de Teste**
   - **Plano de Teste (Test Plan)** é o componente básico onde você irá definir os testes.
   - No JMeter, você verá a interface com um plano de teste em branco.
     - Clique com o botão direito no **Test Plan** no painel da esquerda.
     - Selecione **Add > Threads (Users) > Thread Group**.
     - O **Thread Group** é onde você define o número de usuários virtuais (threads) que irão simular a carga.

### 3. **Configurar o Thread Group**
   - **Thread Group** define os parâmetros do teste, como o número de usuários e a duração.
     - **Número de Threads (Usuários)**: Quantos usuários virtuais irão realizar o teste (exemplo: 10).
     - **Período de Ramp-Up**: O tempo que o JMeter vai levar para iniciar todas as threads (por exemplo, 10 segundos). Se o número de threads for 10 e o ramp-up for 10 segundos, o JMeter iniciará 1 thread por segundo.
     - **Loop Count**: Número de vezes que cada thread vai executar o seu teste. Se você definir 1, cada thread realizará a requisição uma vez. Se você quiser repetir a ação 10 vezes, coloque 10.

### 4. **Adicionar um Sampler (Requisição)**
   Agora, vamos definir qual requisição será enviada para o servidor.

   - **Exemplo simples: requisição HTTP**
     - Clique com o botão direito em **Thread Group** > **Add > Sampler > HTTP Request**.
     - **Configuração HTTP Request**:
       - **Server Name or IP**: Insira o domínio ou o IP do servidor para o qual a requisição será enviada (exemplo: `www.exemplo.com`).
       - **Port Number**: Deixe em branco se o servidor usar a porta padrão (80 para HTTP ou 443 para HTTPS).
       - **Method**: Escolha o tipo de requisição, como **GET**, **POST**, etc.
       - **Path**: O caminho para o recurso que você deseja acessar no servidor (exemplo: `/pagina-de-exemplo`).

### 5. **Adicionar um Listener para Visualizar os Resultados**
   Para ver os resultados do seu teste, você precisa adicionar um **Listener**.

   - Clique com o botão direito em **Thread Group** > **Add > Listener > View Results Tree**.
   - Este listener exibe os resultados detalhados de cada requisição, incluindo sucesso ou falha.

### 6. **Rodar o Teste**
   - Após configurar seu **Thread Group**, **HTTP Request** e **Listener**, você pode rodar o teste.
   - Clique no ícone de **Play** (a seta verde) no topo da interface.
   - O JMeter começará a enviar requisições conforme a configuração de threads e exibirá os resultados no **View Results Tree**.

### 7. **Verificar os Resultados**
   - No **View Results Tree**, você verá os detalhes das requisições enviadas, incluindo o tempo de resposta, o código de status HTTP (por exemplo, 200 para sucesso) e o conteúdo retornado.
   - Isso ajuda a verificar se o seu site ou API está respondendo corretamente e com o tempo de resposta esperado.

### 8. **Ajustar e Expandir o Teste**
   Agora que você criou seu primeiro teste básico, pode expandi-lo:
   - **Adicionar mais requisições**: Se você quiser simular uma navegação mais realista (clicando em links, preenchendo formulários), adicione mais **HTTP Requests** ou outros tipos de Samplers.
   - **Adicionar Assertions**: Para validar se a resposta está correta, adicione **Assertions** (como **Response Assertion**) para verificar o conteúdo da resposta.

### 9. **Salvar o Plano de Teste**
   - Quando terminar, salve o seu plano de teste clicando em **File > Save** ou pressionando **Ctrl + S**.

### Exemplo Completo:
Aqui está um resumo rápido da estrutura do seu teste simples:

- **Test Plan**
  - **Thread Group**
    - **HTTP Request** (Configuração: método GET, servidor, e caminho)
    - **View Results Tree**

### Dica:
Se você quiser realizar testes mais avançados, como testar APIs REST, gerar relatórios de desempenho ou adicionar mais complexidade ao seu teste, pode começar a explorar outros tipos de **Samplers**, **Listeners**, **Pre-Processors** e **Post-Processors** que o JMeter oferece.
