Aqui está o manual detalhado para criar um cenário de teste **PATCH** no JMeter usando a interface gráfica, sem recorrer à linha de comando.

---

# Manual: Criando um Cenário de Teste PATCH no JMeter

Este manual descreve como criar um cenário de teste HTTP PATCH no JMeter utilizando a interface gráfica, sem utilizar a linha de comando.

## Passos para Criar o Cenário de Teste PATCH

### 1. **Abrir o JMeter**

- **Inicie o JMeter**: Vá até o diretório onde o JMeter foi instalado e execute o arquivo `jmeter.bat` (Windows) ou `jmeter` (Linux/macOS) dentro da pasta `bin`.
  
- A interface gráfica do JMeter será aberta. Agora, vamos começar a configurar o teste PATCH.

---

### 2. **Adicionar um Plano de Teste**

O **Plano de Teste** (Test Plan) é o primeiro elemento que organiza os testes no JMeter.

1. No painel esquerdo (árvore de elementos), **clique com o botão direito sobre "Test Plan"**.
   
2. Selecione **Add** > **Threads (Users)** > **Thread Group**.

Isso cria um **Thread Group** no seu Plano de Teste, que vai controlar os usuários virtuais (threads), o tempo de inicialização e o número de repetições.

---

### 3. **Configurar o Thread Group**

O **Thread Group** define como os usuários virtuais irão interagir com o servidor durante o teste.

- **Number of Threads (Usuários)**: Define quantos usuários simultâneos você deseja simular.
- **Ramp-Up Period (em segundos)**: Define o tempo que o JMeter vai levar para iniciar todas as threads. Por exemplo, se você definir 10 threads e 10 segundos, o JMeter vai iniciar 1 thread por segundo até atingir 10 threads.
- **Loop Count**: Define o número de vezes que o teste será executado. Se você configurar 5 loops, o JMeter vai executar o teste 5 vezes.

---

### 4. **Adicionar um Sampler HTTP Request (PATCH)**

Agora, vamos adicionar o **HTTP Request Sampler**, que fará a requisição PATCH.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Sampler** > **HTTP Request**.

2. No painel central, preencha os seguintes campos:

   - **Name**: Dê um nome ao request, como "PATCH Request".
   - **Server Name or IP**: Informe o domínio ou IP do servidor para onde a requisição PATCH será enviada (por exemplo, `www.exemplo.com`).
   - **Port Number**: Se necessário, informe a porta (geralmente `80` para HTTP ou `443` para HTTPS).
   - **Protocol**: Selecione `http` ou `https`, dependendo do protocolo do servidor.
   - **Method**: Selecione `PATCH` no menu suspenso.
   - **Path**: Informe o caminho do recurso que será atualizado. Por exemplo, `/api/atualizar-dados/123`, onde `123` é o ID do recurso a ser modificado.

### 5. **Adicionar Dados no Corpo da Requisição (Body Data)**

O HTTP PATCH geralmente envia dados parciais no corpo da requisição (request body). Para adicionar esses dados:

1. No **HTTP Request**, role para baixo até a seção **Body Data**.

2. Marque a opção **Send Parameters With the Request** (ou **Body Data**).

3. Digite os dados que deseja enviar. Por exemplo, para atualizar parcialmente os dados de um usuário, você poderia enviar algo como:

   ```json
   {
     "email": "novo_email@exemplo.com"
   }
   ```

   Este é um exemplo de uma requisição PATCH que envia apenas um campo parcialmente modificado (no caso, o email).

---

### 6. **Adicionar um Header Manager (Cabeçalhos HTTP)**

Para simular cabeçalhos HTTP adequados, como `Content-Type` (comum em PATCH requests), você pode adicionar um **HTTP Header Manager**.

1. **Clique com o botão direito no "HTTP Request"** e selecione **Add** > **Config Element** > **HTTP Header Manager**.

2. No **HTTP Header Manager**, adicione os cabeçalhos necessários. Por exemplo:

   - **Name**: `Content-Type`
   - **Value**: `application/json` (geralmente usado para dados JSON, mas pode variar dependendo da API).

   Se for necessário usar autenticação (como um token de autenticação), você pode adicionar um cabeçalho como:

   - **Name**: `Authorization`
   - **Value**: `Bearer <seu_token>`

---

### 7. **Adicionar um Listener para Visualizar os Resultados**

Agora, você precisa de um **Listener** para visualizar os resultados do seu teste PATCH.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Listener** > **View Results Tree**.
   
   O **View Results Tree** mostrará todos os detalhes de cada requisição e resposta, incluindo o código de status HTTP, o corpo da resposta e outros dados importantes.

2. Outros listeners úteis que você pode adicionar incluem:
   - **Summary Report**: Exibe um resumo das métricas de performance, como tempo de resposta, taxa de erro, throughput, etc.
   - **Graph Results**: Exibe os resultados do teste em gráficos.

---

### 8. **Salvar o Teste**

Após configurar o seu cenário de teste PATCH, é importante salvar o seu plano de teste.

1. Vá até **File** > **Save** e escolha um nome e local para salvar o arquivo `.jmx`.

---

### 9. **Executar o Teste**

Agora que o cenário de teste PATCH está configurado, você pode executá-lo.

1. **Clique no ícone verde de “Start”** (ícone de play no topo).
2. O JMeter começará a enviar as requisições PATCH conforme as configurações do **Thread Group**.

---

### 10. **Analisar os Resultados**

Após a execução do teste, você pode analisar os resultados utilizando os **Listeners**.

- **View Results Tree**: Mostra detalhes de cada requisição, como o código de status HTTP, o corpo da resposta e os dados retornados.
- **Summary Report**: Fornece uma visão geral das métricas do teste, incluindo tempo médio de resposta, taxa de erro, throughput, etc.

---

## Considerações Finais

- O método PATCH é utilizado para modificar recursos de forma parcial. Ao configurar esse tipo de requisição, é importante garantir que os dados enviados no corpo da requisição (Body Data) estejam corretos e no formato esperado pela API.
  
- A configuração de **Cabeçalhos HTTP** é essencial para garantir que a requisição seja interpretada corretamente pelo servidor, especialmente se a API utilizar autenticação ou tipos específicos de dados.

- Utilize **Timers** para simular intervalos entre as requisições e obter resultados mais realistas do desempenho da API.

