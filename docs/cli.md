## CLI

Para executar um teste do JMeter via linha de comando, siga as etapas abaixo:

### 1. **Preparação do Teste**

Certifique-se de que você tenha o arquivo de teste `.jmx` salvo em seu sistema. Este é o arquivo que contém o plano de teste do JMeter.

### 2. **Acessar o Diretório do JMeter**

Abra um terminal ou prompt de comando e navegue até o diretório onde o JMeter está instalado. Normalmente, o arquivo executável `jmeter` (ou `jmeter.bat` no Windows) está localizado na pasta `bin`.

Por exemplo:

- No **Windows**, o arquivo `jmeter.bat` está em `C:\jmeter\bin`.
- No **Linux/macOS**, o arquivo `jmeter` está em `/home/user/jmeter/bin`.

### 3. **Comando para Executar o Teste**

Use o seguinte comando para executar o teste no JMeter via linha de comando:

```bash
jmeter -n -t /caminho/do/arquivo/teste.jmx -l /caminho/do/arquivo/resultados.jtl
```

#### Explicação dos parâmetros:

- `-n`: Executa o JMeter em modo não gráfico (modo de linha de comando).
- `-t /caminho/do/arquivo/teste.jmx`: Especifica o caminho para o arquivo de teste JMX que você deseja executar.
- `-l /caminho/do/arquivo/resultados.jtl`: Define o arquivo de saída onde os resultados do teste serão salvos (no formato `.jtl`).

### Exemplo de Comando

Se o arquivo JMX estiver localizado em `C:\jmeter\testes\teste.jmx` e você deseja salvar os resultados em `C:\jmeter\resultados\saida.jtl`, o comando seria:

```bash
jmeter -n -t C:\jmeter\testes\teste.jmx -l C:\jmeter\resultados\saida.jtl
```

### 4. **Opções Adicionais**

Você também pode adicionar outras opções, como:

- **`-J`** para passar parâmetros de propriedades:

    ```bash
    jmeter -n -t /caminho/do/arquivo/teste.jmx -l /caminho/do/arquivo/resultados.jtl -JnomeParametro=valor
    ```

- **`-R`** para especificar servidores remotos para execução distribuída:

    ```bash
    jmeter -n -t /caminho/do/arquivo/teste.jmx -l /caminho/do/arquivo/resultados.jtl -Rhost1,host2
    ```

- **`-e`** para gerar o relatório em formato HTML após a execução do teste:

    ```bash
    jmeter -n -t /caminho/do/arquivo/teste.jmx -l /caminho/do/arquivo/resultados.jtl -e -o /caminho/do/relatorio
    ```

Isso gerará um relatório visual em HTML com base nos resultados do teste.

### 5. **Verificando os Resultados**

Após a execução do teste, você pode abrir o arquivo `.jtl` (gerado com a opção `-l`) em um editor de texto ou importar os dados para ferramentas de análise, como o [JMeter Dashboard](https://jmeter.apache.org/usermanual/generating-dashboard.html) (gerado com `-e -o`), ou usar o próprio JMeter para visualizar os resultados.

---

Com essas etapas, você pode executar testes do JMeter em linha de comando, o que é útil para automação de testes e integração contínua.