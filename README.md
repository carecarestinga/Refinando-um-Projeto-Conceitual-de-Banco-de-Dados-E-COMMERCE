# Projeto Conceitual de Banco de Dados - E-Commerce

## Descrição do Desafio

Este projeto tem como objetivo refinar o modelo conceitual de um banco de dados para um sistema de e-commerce. O banco de dados deve ser capaz de armazenar informações sobre clientes, formas de pagamento, status de entregas e outros dados necessários para o funcionamento de uma loja virtual.

As mudanças foram implementadas no modelo para atender às seguintes exigências:

- **Cliente PJ e PF**: A conta do cliente pode ser de Pessoa Física (PF) ou Pessoa Jurídica (PJ), mas não pode haver uma conta que possua ambos os tipos de cliente simultaneamente.
  
- **Pagamento**: Um cliente pode ter mais de uma forma de pagamento registrada em sua conta, permitindo flexibilidade na escolha do método de pagamento.

- **Entrega**: A entrega agora tem atributos adicionais, como o **status** (em andamento, finalizada, etc.) e um **código de rastreio** para acompanhamento da entrega.

## Objetivo

O objetivo deste projeto é criar um modelo de banco de dados eficaz para um e-commerce, garantindo que ele suporte múltiplos tipos de clientes (PJ e PF), permita várias formas de pagamento e forneça dados de rastreio para entregas. Além disso, o banco de dados deve ser flexível o suficiente para escalar conforme o crescimento do e-commerce.

## Implementação

### Passos para Implementação:

1. **Cliente**:
   - A tabela de `Cliente` foi dividida para diferenciar clientes PJ e PF. Foi criada uma relação entre a tabela `Cliente` e uma tabela `TipoCliente`, onde cada cliente pode ser categorizado como PF ou PJ.
   - Campos como `cpf` e `cnpj` foram adicionados para garantir que a validação de cada tipo de cliente seja feita corretamente.

2. **Pagamento**:
   - A tabela `Pagamento` foi ajustada para permitir múltiplos registros de pagamento para cada cliente. Isso foi feito através de um relacionamento entre a tabela `Cliente` e `Pagamento`, utilizando uma chave estrangeira para associar os métodos de pagamento ao cliente.
   - Cada registro de pagamento inclui detalhes como tipo de pagamento (cartão de crédito, boleto, etc.), data de pagamento e status.

3. **Entrega**:
   - A tabela `Entrega` foi expandida para incluir um campo `status` (em andamento, finalizada, pendente) e um campo `codigo_rastreio` para armazenar o código utilizado para rastrear o pacote.

### Alterações no Modelo de Banco de Dados:

- **Cliente**: A tabela de cliente foi modificada para distinguir PF de PJ. Adicionamos o atributo tipo_cliente para  específicar os clientes PJ e PF.
- **Pagamento**: Agora um cliente pode ter múltiplos métodos de pagamento, com um relacionamento de um para muitos entre `Cliente` e `Pagamento`.
- **Entrega**: A tabela de entregas agora tem os campos `status` e `codigo_rastreio`, permitindo o acompanhamento da entrega.

### Diagrama de Entidades e Relacionamentos

O diagrama atualizado do banco de dados pode ser visualizado nos arquivos `diagrama-e-commerce-refinado.mwb` (arquivo do MySQL Workbench) e `diagrama-e-commerce-aula-refinado.png` (imagem). Esses diagramas ilustram as relações entre as tabelas de `Cliente`, `Pagamento`, `Entrega`, entre outras, com as novas modificações implementadas.

## Tecnologias Utilizadas

- MySQL Workbench
- GitHub (para controle de versão e armazenamento do projeto)
- Diagramas ER (para visualização do banco de dados)

## Como Rodar o Projeto

1. Clone este repositório para sua máquina local:
