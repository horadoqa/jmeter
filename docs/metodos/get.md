# Manual: Criando um Cenário de Teste GET no JMeter

Este manual descreve como criar um cenário de teste HTTP GET no JMeter, sem usar a linha de comando, utilizando a interface gráfica do JMeter.

## Passos para Criar o Cenário de Teste GET

### 1. **Abrir o JMeter**

- **Inicie o JMeter**: Vá até a pasta onde o JMeter foi instalado e execute o arquivo `jmeter.bat` (no Windows) ou `jmeter` (no Linux/macOS) na pasta `bin`.
  
- O JMeter será iniciado com uma interface gráfica. A partir daqui, você começará a configurar o seu teste.

---

### 2. **Adicionar um Plano de Teste**

O **Plano de Teste** (Test Plan) é o primeiro item que você deve configurar. Ele contém toda a estrutura de testes.

1. No painel esquerdo (árvore de elementos), **clique com o botão direito sobre "Test Plan"**.
   
2. Selecione **Add** > **Threads (Users)** > **Thread Group**.

Isso adiciona um **Thread Group** ao seu Plano de Teste. O **Thread Group** define o número de usuários virtuais (threads), o tempo de ramp-up e o número de repetições de execução de cada requisição.

---

### 3. **Configurar o Thread Group**

O **Thread Group** vai definir o comportamento dos usuários simulados que farão o teste de carga. Você pode configurar o número de threads (usuários virtuais), o tempo de inicialização e o número de iterações.

- **Number of Threads (Usuarios)**: Define quantos usuários simultâneos você quer simular.
- **Ramp-Up Period (em segundos)**: O tempo que o JMeter leva para iniciar todos os usuários. Exemplo: se você definir 10 threads e 10 segundos, o JMeter começará 1 thread por segundo até atingir 10 threads.
- **Loop Count**: Número de vezes que o teste será executado. Deixe em 1 para executar uma vez ou configure conforme necessário.

### 4. **Adicionar um Sampler HTTP Request**

Agora, vamos adicionar o **HTTP Request Sampler** que irá simular a requisição GET.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Sampler** > **HTTP Request**.

2. No painel central, preencha os seguintes campos:

   - **Name**: Nome do request, por exemplo, "GET Request".
   - **Server Name or IP**: O domínio ou IP do servidor para onde a requisição GET será enviada (exemplo: `www.exemplo.com`).
   - **Port Number**: A porta do servidor (por exemplo, `80` para HTTP ou `443` para HTTPS, caso não seja especificada no URL).
   - **Protocol**: Selecione `http` ou `https`, conforme o protocolo utilizado pelo servidor.
   - **Method**: Selecione `GET` no campo de método HTTP.
   - **Path**: O caminho do recurso que será acessado (exemplo: `/api/dados`).

Exemplo de uma requisição GET simples:
   - **Server Name or IP**: `www.exemplo.com`
   - **Port Number**: `80`
   - **Method**: `GET`
   - **Path**: `/api/dados`

---

### 5. **Adicionar um Listener para Visualizar os Resultados**

Para visualizar os resultados do teste, você precisa adicionar um Listener. O Listener coleta os resultados da execução do teste e permite visualizá-los de diversas formas.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Listener** > **View Results Tree**.
   
   O **View Results Tree** permite visualizar os detalhes das requisições e respostas, incluindo o conteúdo e o status das respostas.

2. Você também pode adicionar outros listeners, como:
   - **Summary Report**: Para ver um resumo estatístico das requisições.
   - **Graph Results**: Para ver os resultados em gráficos.

---

### 6. **Configurar os Headers (Opcional)**

Se você precisar adicionar cabeçalhos HTTP (headers), como autenticação ou customizações, siga os passos abaixo:

1. **Clique com o botão direito no "HTTP Request"** e selecione **Add** > **Config Element** > **HTTP Header Manager**.

2. No **HTTP Header Manager**, adicione os cabeçalhos necessários, como:

   - **Name**: `Content-Type`
   - **Value**: `application/json` (ou outro tipo, conforme necessário)

---

### 7. **Configurar Tempo de Atraso (Opcional)**

Se você precisar simular um tempo de espera entre as requisições, pode configurar um **Timer**.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Timer** > **Constant Timer**.

2. Configure o tempo de atraso em milissegundos, por exemplo, `1000` (para 1 segundo de atraso entre cada requisição).

---

### 8. **Salvar o Teste**

Após configurar o seu cenário de teste, salve o seu plano de teste.

- Vá até **File** > **Save** e escolha um nome e local para o arquivo `.jmx`.

---

### 9. **Executar o Teste**

Agora você pode executar o teste de carga com a configuração do HTTP GET.

1. **Clique no botão verde de “Start”** (ícone de play no topo).
2. O JMeter começará a simular as requisições GET conforme os parâmetros configurados no **Thread Group**.

---

### 10. **Analisar os Resultados**

Após a execução do teste, você pode visualizar os resultados através dos Listeners adicionados.

- **View Results Tree** mostrará uma árvore com detalhes de cada requisição, incluindo os códigos de resposta e os dados da resposta.
- **Summary Report** mostrará uma visão geral com dados como a quantidade de requisições realizadas, o tempo médio, o tempo máximo, a taxa de erro, entre outros.

---

## Considerações Finais

- O JMeter permite a criação de cenários de teste HTTP GET muito flexíveis, onde você pode simular múltiplos usuários, controlar os tempos de resposta e até fazer configurações mais avançadas, como adicionar parâmetros, cabeçalhos HTTP ou autenticação.
  
- Ao executar testes mais complexos, considere usar diferentes **Thread Groups** para simular cenários distintos ou adicionar **Controllers** para criar fluxos de teste mais dinâmicos (como **If Controllers**, **Loop Controllers**, etc.).

