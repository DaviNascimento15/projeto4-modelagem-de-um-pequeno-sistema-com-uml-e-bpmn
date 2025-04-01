# projeto4-modelagem-de-um-pequeno-sistema-com-uml-e-bpmn

# Projeto de matriz UML e PBMN
o modelo criado tem como base um usuario reservando uma ou mais reservas de um restaurante.
## INTEGRANTES DA EQUIPE:
- Davi Nascimento

Modelo UML 

                +-------------------+                           +-------------------+                           +-------------------+
                     USUÁRIO                                          COMPRA                                       PRODUTO
                +-------------------+                           +-------------------+                           +-------------------+
                - id: int                                     - id: int                                     - id: int
                - nome: String                                - data: Date                                 - nome: String
                - email: String                               - status: String                             - preço: float
                +-------------------+                           +-------------------+                           +-------------------+
                + cadastrar()                                 + confirmar()                                 + listarProdutos()
                + cancelarCompra()                            + cancelar()                                  + verificarEstoque()
                +-------------------+                           +-------------------+                           +-------------------+
                
                      1                                            N                           1               N
                +-------------------+---------------------------+------------------------+--------------------+
                | Um Usuário pode fazer várias Compras         | Um Produto pode estar em várias Compras      |
                +-------------------+---------------------------+------------------------+--------------------+


Modelo BPMN

    graph TD;
    A[Início] --> B[Usuário acessa o sistema]
    B --> C[Seleciona Produto]
    C --> D[Adiciona ao carrinho]
    D --> E[Verifica disponibilidade]
    E -- Disponível --> F[Confirma compra]
    E -- Não disponível --> C
    F --> G[Compra registrada]
    G --> H[Fim]
