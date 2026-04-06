# 🚗 Car Rental System (Sistema de Aluguel de Carros)

## 📖 Sobre o Projeto
Este projeto é uma aplicação de console desenvolvida em **Java** que simula as regras de faturamento de uma locadora de veículos. O sistema calcula dinamicamente o valor do aluguel com base na duração estipulada e insere os descontos/taxas relativas aos impostos brasileiros vigentes (Simulados na classe de serviço de taxa).

O projeto aplica fortemente os conceitos e pilares da **Programação Orientada a Objetos (POO)**.

## 🛠️ Tecnologias e Conceitos
- **Linguagem:** Java 8+
- **Manipulação de Tempo:** `java.time.LocalDateTime` e `java.time.format.DateTimeFormatter`
- **Conceitos de Arquitetura e POO:**
  - Separação de responsabilidades (Entities vs Services)
  - Composição de Objetos (CarRental contendo Vehicle e Invoice)
  - Injeção de dependência e Inversão de Controle usando Interfaces (`TaxService`, `BrazilTaxService`)

## ⚙️ Funcionalidades
1. O usuário informa os dados da locação:
   - **Modelo do carro**
   - **Data e hora de retirada** (formato: `dd/MM/yyyy HH:mm`)
   - **Data e hora de devolução** (formato: `dd/MM/yyyy HH:mm`)
2. São definidos os preços operacionais da locadora:
   - Valor do Aluguel por Hora
   - Valor do Aluguel por Dia
3. O serviço de locação gera a **Fatura (Invoice)** contendo:
   - Pagamento Básico correspondente ao tempo de uso
   - Imposto calculado sobre o pagamento básico
   - Pagamento Total

## 🚀 Como Executar

1. Certifique-se de ter o **Java (JDK)** instalado.
2. No seu terminal, acesse a pasta contendo o código fonte:
   ```bash
   cd src
   ```
3. Compile todas as classes e dependências:
   ```bash
   javac application/Program.java model/entities/*.java model/services/*.java
   ```
4. Execute o arquivo principal da aplicação:
   ```bash
   java application.Program
   ```

## 📂 Arquitetura de Pastas
A organização dos pacotes foi montada isolando a lógica de negócio dos modelos de dados:
- `application/`: Contém a classe principal `Program.java`, ponto de partida da simulação no terminal.
- `model.entities/`: Modelos e entidades do domínio: `Vehicle`, `Invoice` e `CarRental`.
- `model.services/`: Regras de negócio, serviços computacionais e abstrações como o `RentalService` e interface `TaxService`.
