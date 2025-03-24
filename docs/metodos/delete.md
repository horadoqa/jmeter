# Manual: Criando um Cenário de Teste DELETE no JMeter

Este manual descreve como criar um cenário de teste HTTP DELETE no JMeter utilizando a interface gráfica, sem utilizar a linha de comando.

## Passos para Criar o Cenário de Teste DELETE

### 1. **Abrir o JMeter**

- **Inicie o JMeter**: Vá até o diretório onde o JMeter foi instalado e execute o arquivo `jmeter.bat` (Windows) ou `jmeter` (Linux/macOS) dentro da pasta `bin`.
  
- A interface gráfica do JMeter será aberta. Agora, vamos começar a configurar o teste DELETE.

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

### 4. **Adicionar um Sampler HTTP Request (DELETE)**

Agora, vamos adicionar o **HTTP Request Sampler**, que fará a requisição DELETE.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Sampler** > **HTTP Request**.

2. No painel central, preencha os seguintes campos:

   - **Name**: Dê um nome ao request, como "DELETE Request".
   - **Server Name or IP**: Informe o domínio ou IP do servidor para onde a requisição DELETE será enviada (por exemplo, `www.exemplo.com`).
   - **Port Number**: Se necessário, informe a porta (geralmente `80` para HTTP ou `443` para HTTPS).
   - **Protocol**: Selecione `http` ou `https`, dependendo do protocolo do servidor.
   - **Method**: Selecione `DELETE` no menu suspenso.
   - **Path**: Informe o caminho do recurso que será excluído. Por exemplo, `/api/deletar-item/123`, onde `123` pode ser o ID do item a ser excluído.

### 5. **Adicionar um Header Manager (Cabeçalhos HTTP)**

Caso seja necessário adicionar cabeçalhos HTTP, como `Authorization` ou `Content-Type`, você pode usar o **HTTP Header Manager**.

1. **Clique com o botão direito no "HTTP Request"** e selecione **Add** > **Config Element** > **HTTP Header Manager**.

2. No **HTTP Header Manager**, adicione os cabeçalhos necessários. Por exemplo:

   - **Name**: `Authorization`
   - **Value**: `Bearer <seu_token>` (se a API exigir autenticação via token).
   
   Ou se for necessário informar o tipo de dado:

   - **Name**: `Content-Type`
   - **Value**: `application/json` (se a API estiver esperando um JSON ou outro tipo).

   Se a API não exigir cabeçalhos adicionais, você pode omitir essa etapa.

---

### 6. **Adicionar um Listener para Visualizar os Resultados**

Agora, você precisa de um **Listener** para visualizar os resultados do seu teste DELETE.

1. **Clique com o botão direito no "Thread Group"** e selecione **Add** > **Listener** > **View Results Tree**.
   
   O **View Results Tree** exibirá todos os detalhes de cada requisição e resposta, como o código de status HTTP, corpo da resposta e cabeçalhos.

2. Outros listeners úteis que você pode adicionar incluem:
   - **Summary Report**: Exibe um resumo das métricas de performance, como tempo de resposta, taxa de erro, throughput, etc.
   - **Graph Results**: Exibe gráficos com os resultados do teste.

---

### 7. **Salvar o Teste**

Após configurar o seu cenário de teste DELETE, salve o seu plano de teste.

1. Vá até **File** > **Save** e escolha um nome e local para salvar o arquivo `.jmx`.

---

### 8. **Executar o Teste**

Agora que o cenário de teste DELETE está configurado, você pode executá-lo.

1. **Clique no ícone verde de “Start”** (ícone de play no topo).
2. O JMeter começará a enviar as requisições DELETE conforme a configuração do **Thread Group**.

---

### 9. **Analisar os Resultados**

Após a execução do teste, você pode analisar os resultados utilizando os **Listeners**.

- **View Results Tree**: Mostra detalhes de cada requisição, incluindo o código de status HTTP, o corpo da resposta e outros detalhes importantes.
- **Summary Report**: Fornece um resumo estatístico das requisições, incluindo o tempo médio de resposta, taxa de erro, throughput, entre outras métricas.

---

## Considerações Finais

- O método DELETE é utilizado para remover um recurso do servidor. É importante garantir que o **Path** da requisição esteja correto e que o servidor esteja configurado para permitir a remoção de dados via esse método.
  
- A configuração de **Cabeçalhos HTTP** é fundamental, especialmente em APIs que requerem autenticação ou utilizam tipos específicos de conteúdo.

- Ao testar APIs DELETE, você pode querer configurar os testes para garantir que os dados sejam realmente removidos (por exemplo, verificando se um GET posterior ao DELETE retorna erro ou "recurso não encontrado").

- Lembre-se de utilizar **Timers** para simular o comportamento real dos usuários, evitando enviar requisições de forma muito rápida e prejudicando a precisão dos testes.

