# Manual: Criando um Cenário de Teste POST no JMeter

Este manual descreve como criar um cenário de teste HTTP POST no JMeter utilizando a interface gráfica, sem utilizar a linha de comando.

## Passos para Criar o Cenário de Teste POST

### 1. **Abrir o JMeter**

- **Inicie o JMeter**: Vá até o diretório onde o JMeter foi instalado e execute o arquivo `jmeter.bat` (Windows) ou `jmeter` (Linux/macOS) dentro da pasta `bin`.
  
- A interface gráfica do JMeter será aberta. Agora, vamos começar a configurar o teste POST.

---

### 2. **Adicionar um Plano de Teste**

O **Plano de Teste** (Test Plan) é o elemento raiz que organiza os testes no JMeter.

1. No painel esquerdo (árvore de elementos), **clique com o botão direito sobre "Test Plan"**.
   
2. Selecione **Add** > **Threads (Users)** > **Thread Group**.

Isso cria um **Thread Group** no seu Plano de Teste, que vai controlar os usuários virtuais (threads), o tempo de inicialização e o número de repetições.

---

### 3. **Configurar o Thread Group**

O **Thread Group** define como os usuários virtuais vão interagir com o servidor durante o teste.

- **Number of Threads (Usuarios)**: Define quantos usuários simultâneos você deseja simular.
- **Ramp-Up Period (em segundos)**: Define o tempo de início para criar todas as threads. Por exemplo, se você definir 10 threads e 10 segundos, o JMeter vai iniciar 1 thread por segundo até atingir 10 threads.
- **Loop Count**: Define o número de repetições do teste. Por exemplo, se você configurar 5 loops, o JMeter vai executar o teste 5 vezes.

---

### 4. **Adicionar um Sampler HTTP Request (POST)**

Agora, vamos adicionar o **HTTP Request Sampler**, que fará a requisição POST.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Sampler** > **HTTP Request**.

2. No painel central, preencha os seguintes campos:

   - **Name**: Dê um nome ao request, como "POST Request".
   - **Server Name or IP**: Informe o domínio ou IP do servidor (por exemplo, `www.exemplo.com`).
   - **Port Number**: Se necessário, especifique a porta (geralmente `80` para HTTP e `443` para HTTPS).
   - **Protocol**: Selecione `http` ou `https` conforme o protocolo do servidor.
   - **Method**: Selecione `POST` no menu suspenso.
   - **Path**: Informe o caminho para o recurso (exemplo: `/api/login`).

### 5. **Adicionar Dados no Corpo da Requisição (Body Data)**

O HTTP POST geralmente envia dados no corpo da requisição (request body). Para adicionar esses dados:

1. No **HTTP Request**, role para baixo até a seção **Body Data**.
   
2. Marque a opção **Send Parameters With the Request** (ou **Body Data**).

3. Digite os parâmetros que deseja enviar. Por exemplo:

   ```
   username=usuario_teste&password=senha123
   ```

   Este é um exemplo de uma requisição POST que envia um par de parâmetros (`username` e `password`) para o servidor.

---

### 6. **Adicionar um Header Manager (Cabeçalhos HTTP)**

Para simular um cabeçalho HTTP adequado, como `Content-Type` (muito comum em POST requests), você pode adicionar um **HTTP Header Manager**.

1. **Clique com o botão direito no "HTTP Request"** e selecione **Add** > **Config Element** > **HTTP Header Manager**.

2. No **HTTP Header Manager**, adicione o cabeçalho necessário. Por exemplo, se você estiver enviando dados em formato JSON, o cabeçalho seria:

   - **Name**: `Content-Type`
   - **Value**: `application/x-www-form-urlencoded` (ou `application/json`, dependendo da sua API)

   Se você estiver usando autenticação, pode adicionar um cabeçalho como:

   - **Name**: `Authorization`
   - **Value**: `Bearer <seu_token>`

---

### 7. **Adicionar um Listener para Visualizar os Resultados**

Agora, você precisa de um **Listener** para visualizar os resultados do seu teste.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Listener** > **View Results Tree**.
   
   O **View Results Tree** exibirá detalhes de cada requisição e resposta (código de status, dados retornados, etc.).

2. Você também pode adicionar outros listeners, como:
   - **Summary Report**: Exibe uma visão geral estatística das requisições.
   - **Graph Results**: Exibe os resultados em gráficos.

---

### 8. **Salvar o Teste**

Após configurar seu cenário de teste, é importante salvar o plano de teste para futura execução.

1. Vá até **File** > **Save** e escolha um nome e local para salvar o arquivo `.jmx`.

---

### 9. **Executar o Teste**

Agora que o cenário de teste POST está configurado, você pode executá-lo.

1. **Clique no ícone verde de “Start”** (ícone de play no topo).
2. O JMeter começará a enviar as requisições POST de acordo com a configuração do **Thread Group**.

---

### 10. **Analisar os Resultados**

Após a execução do teste, você pode analisar os resultados através dos **Listeners**.

- **View Results Tree**: Mostra todos os detalhes das requisições e respostas, incluindo o conteúdo da resposta.
- **Summary Report**: Fornece uma visão geral do desempenho, com métricas como tempo médio de resposta, taxa de erro, throughput, entre outras.

---

## Considerações Finais

- Ao criar um cenário de teste POST, é importante garantir que os dados enviados no corpo da requisição (Body Data) estejam corretamente formatados de acordo com o tipo de API que você está testando (ex: JSON, XML ou `application/x-www-form-urlencoded`).
  
- O JMeter oferece flexibilidade para incluir cabeçalhos, parâmetros, e autenticação, o que permite simular testes de performance para uma grande variedade de APIs POST.

- Lembre-se de usar **Timers** para simular o comportamento real dos usuários (intervalos entre as requisições) e evitar sobrecarregar seu servidor com requisições consecutivas muito rápidas.

