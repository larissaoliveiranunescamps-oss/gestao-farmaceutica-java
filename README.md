# Software de Dispensação Segura e Gestão de Estoque Hospitalar

> **Projeto de Gestão Farmacêutica e Análise Clínica de Segurança Desenvolvido em Java**

O **Software de Dispensação Segura** é uma aplicação Java projetada para otimizar a gestão de estoque em ambiente de Farmácia Hospitalar/UTI e **impedir erros humanos no ponto de dispensação** através da análise automatizada de interações medicamentosas e controle temporal de lotes.

## Diagnóstico do Problema & Regra de Negócio

Em ambientes hospitalares e drogarias, a falha humana durante a triagem e dispensação de medicamentos pode resultar em eventos adversos graves. 

Este software atua como uma **trava de segurança automatizada**, garantindo:
1. **Prevenção de Interações Severas:** Intercepta combinações clínicas de alto risco antes da liberação ao paciente (ex: uso concomitante de *Aspirina* e *Varfarina*).
2. **Controle Estrito de Validades:** Monitoramento contínuo do prazo de expiração dos lotes, sinalizando itens críticos a vencer.
3. **Rastreabilidade de Controlados:** Captura obrigatória de CRM do prescritor e número de receituário para fármacos sujeitos a controle especial (Portaria 344/98).

## Principais Funcionalidades

- **`[1]` Exibição Completa de Estoque:** Relatório detalhado com status de validade calculado dinamicamente em tempo real (`Vencido`, `Próximo da validade - até 60 dias`, ou `Dentro do prazo`).
- **`[2]` Busca por Denominação Comum:** Localização rápida no estoque por nome do fármaco (case-insensitive).
- **`[3]` Cadastro Validado:** Validação estrita de tipos de dados (impede quantidades negativas ou entradas nulas).
- **`[4]` Persistência de Dados:** Leitura e gravação do estado do inventário em arquivos de texto (`.txt`).
- **`[5]` Análise Automatizada de Interações:** Checagem cruzada imediata entre pares de fármacos com alerta clínico imediato.
- **`[6]` Resiliência Hospitalar (Log de Erros):** Tratamento de exceções robusto (`try-catch`) que grava falhas do sistema em um arquivo interno de auditoria (`erros_uti.log`) sem derrubar a aplicação.

## Tecnologias e Conceitos Aplicados

- **Linguagem:** Java 17+
- **Orientação a Objetos (POO):** Encapsulamento, Abstração e Herança (`MedicamentoControlado` estende `Medicamento`).
- **Data e Hora (`java.time`):** Manipulação de datas com `LocalDate` e cálculo temporal de validade com `ChronoUnit.DAYS`.
- **Coleções Dinâmicas:** Uso de `ArrayList` para manipulação em memória.
- **Manipulação de Arquivos (I/O):** Gravação com `PrintWriter` e `FileWriter`.
- **Tratamento de Exceções:** Captura individualizada de `InputMismatchException`, `DateTimeParseException` e `IllegalArgumentException`.

## Execução do Projeto

```bash
   git clone [https://github.com/larissaoliveiranunescamps-oss/gestao-farmaceutica-java.git](https://github.com/larissaoliveiranunescamps-oss/gestao-farmaceutica-java.git)
