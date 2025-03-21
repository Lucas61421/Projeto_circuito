# Relatório sobre o Funcionamento do Circuito e Implementação das Instruções

## 1. Introdução
Este relatório descreve o funcionamento do circuito do processador didático fornecido e detalha a implementação das nove novas instruções especificadas no documento. O processador segue a arquitetura MIPS simplificada e suporta instruções nos formatos R, I e J.


## 2. Estrutura Geral do Circuito
O circuito é composto por:
- *Banco de Registradores (BR)*: Responsável por armazenar valores temporários.
- *Memória de Dados (MD)*: Usada para carregamento e armazenamento de valores na memória.
- *Unidade Lógica e Aritmética (ULA)*: Executa operações matemáticas e lógicas.
- *Program Counter (PC)*: Controla a execução sequencial das instruções.
- *Unidade de Controle*: Decodifica instruções e gera sinais de controle.


## 3. Instruções Implementadas
Foram adicionadas as seguintes instruções ao processador:

### *3.1. AND (Tipo R)*
- Operador: BR[rd] = BR[rs] & BR[rt]
- Implementação: Modifica a ULA para suportar operação de AND bit a bit.

### *3.2. OR (Tipo R)*
- Operador: BR[rd] = BR[rs] | BR[rt]
- Implementação: Modifica a ULA para executar OR bit a bit.

### *3.3. BNE (Tipo I - Branch Not Equal)*
- Operador: if (BR[rs] != BR[rt]) PC = Imm
- Implementação: Expande a unidade de controle para verificar desigualdade e atualizar o PC.

### *3.4. SLTI (Tipo I - Set Less Than Immediate)*
- Operador: if (BR[rs] < Imm) BR[rt] = 1 else BR[rt] = 0
- Implementação: Modifica a ULA para comparar valores e armazenar o resultado.

### *3.5. SLT (Tipo R - Set Less Than)*
- Operador: if (BR[rs] < BR[rt]) BR[rd] = 1 else BR[rd] = 0
- Implementação: Adiciona função de comparação à ULA.

### *3.6. JR (Tipo I - Jump Register)*
- Operador: PC = BR[rs]
- Implementação: Modifica o caminho de dados para permitir a atribuição direta ao PC.

### *3.7. JAL (Tipo J - Jump and Link)*
- Operador: BR[31] = PC + 4; PC = label
- Implementação: Salva o retorno no registrador $ra e atualiza o PC.

### *3.8. SLL (Tipo R - Shift Left Logical)*
- Operador: BR[rt] = BR[rs] << shamt
- Implementação: Modifica a ULA para executar deslocamento para a esquerda.

### *3.9. SLR (Tipo R - Shift Right Logical)*
- Operador: BR[rt] = BR[rs] >> shamt
- Implementação: Modifica a ULA para suportar deslocamento para a direita.


## 4. Conclusão
A implementação das novas instruções expandiu a funcionalidade do processador, permitindo novas operações lógicas, saltos condicionais e manipulação do PC. O circuito atualizado agora pode executar um conjunto mais abrangente de códigos, aproximando-se de uma arquitetura MIPS mais funcional.
