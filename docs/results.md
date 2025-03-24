# RESULTS

Para salvar os resultados dos testes no JMeter, você pode usar **Listeners** que gravam as informações em arquivos de log ou de resultados. O JMeter oferece várias opções para exportar os resultados em diferentes formatos, como **CSV**, **XML** e **JTL**.

Aqui está como você pode salvar os resultados de um teste no JMeter:

## Passos para Salvar os Resultados de Testes no JMeter

### 1. **Adicionar um Listener para Salvar os Resultados**

Primeiro, adicione um **Listener** ao seu plano de teste para que os resultados sejam capturados e salvos.

1. **Clique com o botão direito do mouse no "Thread Group"** (ou no nível desejado onde você quer adicionar o Listener) e selecione **Add** > **Listener**.

2. Escolha o Listener de sua preferência. Alguns dos mais comuns para salvar os resultados incluem:

   - **View Results Tree**: Exibe os resultados de cada requisição, mostrando o corpo da resposta, cabeçalhos e código de status.
   - **Summary Report**: Exibe um resumo estatístico dos testes, como tempo médio de resposta, throughput, taxa de erro, etc.
   - **Simple Data Writer**: Escreve os resultados em um arquivo CSV ou JTL.
   - **Graph Results**: Exibe os resultados do teste em um formato gráfico.
   
   Para salvar os resultados, geralmente, o **Simple Data Writer** ou **Summary Report** são as opções mais adequadas.

### 2. **Configurar o Listener para Salvar em Arquivo**

Agora, vamos configurar um Listener para salvar os resultados em um arquivo. Vamos usar o **Simple Data Writer** como exemplo:

1. **Adicione o Simple Data Writer**:
   - Clique com o botão direito no "Thread Group" e selecione **Add** > **Listener** > **Simple Data Writer**.
   
2. **Configurar o Local e o Formato do Arquivo**:
   - No painel central do **Simple Data Writer**, você verá um campo chamado **Filename**.
   - Clique no botão de navegação ao lado do campo **Filename** e escolha o local onde deseja salvar os resultados.
   - Defina o nome do arquivo de resultados (por exemplo, `resultados_testes.csv`). O JMeter irá salvar os dados no formato CSV ou JTL, dependendo da configuração.
   
   **Exemplo** de caminho de arquivo:
   - `C:\Users\SeuUsuario\Desktop\resultados_testes.csv`
   
3. **Definir o Formato do Arquivo**:
   - O **Simple Data Writer** salva por padrão no formato **CSV** (caso você queira usar **JTL**, basta trocar a extensão do arquivo para `.jtl`).
   - O arquivo CSV conterá informações sobre o tempo de resposta, código de status, número de threads, entre outros dados.

### 3. **Salvar os Resultados em Formatos Diferentes**

Dependendo do Listener, você pode escolher diferentes formatos de arquivo:

- **JTL (JMeter Test Log)**: Formato próprio do JMeter. Contém todos os detalhes de cada requisição, incluindo o tempo de resposta e os dados da resposta.
- **CSV (Comma Separated Values)**: Formato de texto simples, compatível com muitas ferramentas de análise de dados (como Excel, por exemplo).

### 4. **Configuração Avançada de Output (opcional)**

Para configurar o tipo de dados a ser registrado, você pode ir até o Listener **Summary Report** e modificar as opções de saída. Se precisar de detalhes adicionais sobre cada requisição ou se deseja personalizar os resultados, verifique a seção de **Configurações de Resultados**.

- **Field Names**: Defina os nomes dos campos a serem registrados, como `label`, `response time`, `response code`, `latency`, etc.
- **Data Output Format**: Escolha o formato desejado (CSV ou JTL).

### 5. **Executar o Teste e Verificar os Resultados**

Após configurar os Listeners e definir onde salvar os resultados, você pode executar o teste.

1. **Clique no ícone verde de "Start"** (ícone de play no topo).
2. O JMeter começará a executar o teste, e os resultados serão salvos no arquivo especificado.

Após o término do teste, você pode abrir o arquivo CSV ou JTL para analisar os resultados.

### 6. **Exemplo de Formato de Arquivo CSV**

Quando o **Simple Data Writer** é usado, o arquivo CSV gerado terá um formato semelhante a este:

```csv
timeStamp,elapsed,label,responseCode,responseMessage,threadName,dataType,success,bytes,filename,encoding,grpThreads,allThreads,URL,Host,Connect
1648672800000,200,HTTP Request,200,OK,Thread Group 1,text,true,1000,,UTF-8,1,1,http://www.exemplo.com/api/endpoint,www.exemplo.com,200
1648672801000,210,HTTP Request,200,OK,Thread Group 1,text,true,1024,,UTF-8,1,1,http://www.exemplo.com/api/endpoint,www.exemplo.com,210
```

Cada linha contém detalhes sobre uma requisição HTTP, como o tempo de resposta (`elapsed`), o código de resposta (`responseCode`), e outros dados pertinentes.

---

### Considerações Finais

- O JMeter permite salvar os resultados de várias formas, com diversos Listeners e formatos de arquivo. O **Simple Data Writer** é uma escolha popular para exportar os dados em **CSV** ou **JTL**, enquanto o **Summary Report** e **View Results Tree** ajudam a analisar o comportamento das requisições em tempo real.
  
- Para grandes volumes de dados, considere utilizar o **JTL** para armazenar as informações, pois é um formato mais eficiente e fácil de ser manipulado para grandes quantidades de requisições.

- Certifique-se de que o **Listener** esteja configurado corretamente antes de iniciar o teste, para garantir que os dados sejam salvos no local desejado.

Com esses passos, você pode facilmente salvar os resultados dos testes do JMeter e analisá-los para obter insights sobre o desempenho da aplicação.