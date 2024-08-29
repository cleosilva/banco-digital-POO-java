# Projeto de Estudo: Banco Digital em Java

Este projeto é um estudo de Programação Orientada a Objetos (POO) em Java, onde foi implementado um banco digital com funcionalidades básicas de contas bancárias. O projeto explora conceitos como herança, encapsulamento, interfaces, abstração e composição.

## Estrutura do Projeto

O projeto é composto pelas seguintes classes e interfaces:

### 1. `Conta` (Classe Abstrata)
- **Descrição:** Classe base para as contas bancárias, implementa a interface `IConta`.
- **Atributos:**
    - `agencia` (int): Número da agência.
    - `numero` (int): Número da conta.
    - `saldo` (double): Saldo disponível na conta.
    - `cliente` (Cliente): Cliente associado à conta.
- **Métodos:**
    - `sacar(double valor)`: Realiza um saque na conta.
    - `depositar(double valor)`: Realiza um depósito na conta.
    - `transferir(double valor, Conta contaDestino)`: Transfere um valor para outra conta.
    - `imprimirInfoContas()`: Exibe informações básicas da conta.

### 2. `ContaCorrente` (Classe Concreta)
- **Descrição:** Extende a classe `Conta` e representa uma conta corrente.
- **Métodos:**
    - `imprimirExtrato()`: Imprime o extrato da conta corrente.

### 3. `ContaPoupanca` (Classe Concreta)
- **Descrição:** Extende a classe `Conta` e representa uma conta poupança.
- **Métodos:**
    - `imprimirExtrato()`: Imprime o extrato da conta poupança.

### 4. `Cliente` (Classe Concreta)
- **Descrição:** Representa um cliente do banco.
- **Atributos:**
    - `nome` (String): Nome do cliente.

### 5. `Banco` (Classe Concreta)
- **Descrição:** Representa o banco que contém as contas.
- **Atributos:**
    - `nome` (String): Nome do banco.

### 6. `IConta` (Interface)
- **Descrição:** Define os métodos que uma conta bancária deve implementar.
- **Métodos:**
    - `sacar(double valor)`: Realiza um saque.
    - `depositar(double valor)`: Realiza um depósito.
    - `transferir(double valor, Conta contaDestino)`: Transfere um valor para outra conta.
    - `imprimirExtrato()`: Imprime o extrato da conta.

### 7. `Main` (Classe de Execução)
- **Descrição:** Classe principal que executa o programa e demonstra o funcionamento das contas.
- **Exemplo de Uso:**
  ```java
  public class Main {
      public static void main(String[] args) {
          Cliente cliente1 = new Cliente();
          cliente1.setNome("Cleo");

          Conta cc = new ContaCorrente(cliente1);
          cc.depositar(100);

          Conta cp = new ContaPoupanca(cliente1);
          cc.transferir(100, cp);

          cc.imprimirExtrato();
          cp.imprimirExtrato();
      }
  }
  ```
### Como Executar
1. Clone o repositório:
```bash
git clone https://github.com/cleosilva/banco-digital-POO-java.git
```
2. Compile o projeto:
```bash
javac Main.java
```
3. Execute o projeto:
```bash
java Main
```
### Funcionalidades Implementadas
Criar uma conta corrente e uma conta poupança.
Realizar depósitos, saques e transferências entre contas.
Imprimir extratos detalhados de contas.

### Conceitos Abordados
Herança: ContaCorrente e ContaPoupanca herdam de Conta.
Abstração: A classe Conta é abstrata, permitindo a implementação de diferentes tipos de contas.
Interfaces: IConta define o contrato para as operações bancárias.
Encapsulamento: Atributos das classes são privados, acessados através de getters e setters.
Composição: Uma Conta é composta por um Cliente.

### Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

### Licença
Este projeto é licenciado sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.