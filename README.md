# projeto_e_commerce_eer
Refinamento do Projeto Conceitual — E-commerce

Objetivo

Refinar o modelo conceitual de um sistema de e-commerce utilizando o modelo EER (Enhanced Entity Relationship), aplicando conceitos de:

- especialização/generalização,
- herança,
- relacionamentos,
- cardinalidade,
- entidades fortes e fracas.

---

Regras de Negócio Implementadas

Cliente PF e PJ

O sistema permite que um cliente seja:

- Pessoa Física (PF)
  ou
- Pessoa Jurídica (PJ)

Porém:

- um cliente NÃO pode ser os dois simultaneamente.

Para isso foi utilizada uma especialização do tipo DISJOINT.

---

Estrutura de Cliente

Superclasse

Cliente

Atributos:

- idCliente
- endereço
- telefone
- email
- tipoCliente

---

Subclasses

ClientePF

Atributos:

- idCliente
- CPF
- nome

---

ClientePJ

Atributos:

- idCliente
- CNPJ
- razãoSocial

---

Pagamento

O cliente pode cadastrar mais de uma forma de pagamento.

Relacionamento:

- Cliente 1:N Pagamento

Atributos:

- idPagamento
- tipoPagamento
- dadosPagamento

---

Pedido

O cliente pode realizar vários pedidos.

Relacionamento:

- Cliente 1:N Pedido

Atributos:

- idPedido
- statusPedido
- descrição
- frete

---

Produto

Entidade responsável pelos itens vendidos no e-commerce.

Atributos:

- idProduto
- categoria
- descrição
- valor

---

Relação Pedido x Produto

Um pedido pode possuir vários produtos.
Um produto pode estar em vários pedidos.

Relacionamento:

- N:M

Foi criada uma entidade associativa:

PedidoProduto

Atributos:

- idPedido
- idProduto
- quantidade

---

Entrega

Responsável pelo rastreamento e status da entrega.

Relacionamento:

- Pedido 1:1 Entrega

Atributos:

- idEntrega
- statusEntrega
- codigoRastreio

---

Estoque

Responsável pelo controle de disponibilidade dos produtos.

Atributos:

- idEstoque
- localização
- quantidade

---

Fornecedor/Vendedor

Entidade responsável pelo fornecimento dos produtos.

Relacionamentos:

- fornecedor fornece produtos
- vendedor disponibiliza produtos

---

Conceitos Utilizados

Modelo EER

Foram aplicados conceitos do modelo Entidade Relacionamento Estendido:

- superclasse/subclasse
- especialização
- herança
- relacionamento N:M
- entidade associativa

---

Cardinalidades Aplicadas

Relacionamento| Cardinalidade
Cliente → Pedido| 1:N
Cliente → Pagamento| 1:N
Pedido → Produto| N:M
Pedido → Entrega| 1:1

---

Tecnologias Utilizadas

- MySQL Workbench
- Modelo EER
- Modelagem Conceitual

---

Considerações Finais

O projeto foi refinado visando representar de forma mais realista um sistema de e-commerce, aplicando conceitos de modelagem EER para organização e integridade dos dados.
