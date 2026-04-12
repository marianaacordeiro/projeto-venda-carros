# Especificação Técnica (Tech Spec) - Retron

## 1. Modelo de Dados (Diagrama Mermaid)

O sistema utiliza uma estrutura de dados relacional simulada pelo JSON Server, mapeando a relação entre usuários, veículos e registros de interesse.

```mermaid
erDiagram
    USUARIO ||--o{ INTERESSE : "manifesta"
    VEICULO ||--o{ INTERESSE : "recebe"

    USUARIO {
        string id PK
        string nome
        string email
        string telefone
        string cep
        string logradouro
        string bairro
        string cidade
    }

    VEICULO {
        string id PK
        string modelo
        string marca
        int ano
        string preco
        string imagem_url
    }

    INTERESSE {
        string id PK
        string usuario_id FK
        string veiculo_id FK
        string data_registro
    }
````
## 2. Dicionário de Dados
Breve explicação das tabelas principais:

- **Usuários:** Responsável por armazenar os dados cadastrais do cliente e as informações de localização automatizadas.

    - id: Identificador único gerado automaticamente pelo JSON Server (String ou Hash).

    - nome: Nome completo do cliente para personalização da interface.

    - email: Endereço de contato (Chave de validação no front-end).

    - telefone: Número de contato com DDD para retorno comercial.

    - cep: Código postal que dispara a integração com a API ViaCEP.

    - logradouro/bairro/cidade: Dados de endereço preenchidos automaticamente via JavaScript após a consulta do CEP.

- **Veículos:** Contém o catálogo técnico dos carros clássicos disponíveis na vitrine.

    - id: Identificador único do veículo.

    - modelo: Nome do carro (ex: Opala, Maverick).
    
    - marca: Fabricante do veículo.

    - ano: Ano de fabricação (importante para a classificação como clássico/retrô).
    
    - preco: Valor de venda formatado para exibição.

    - imagem_url: Caminho local ou link da fotografia do veículo exibida nos cards.

- **Interesses:** Registra a intenção de compra e gera o lead de venda. Regra de Negócio Crítica: Toda vez que o cliente clicar em "Tenho Interesse", o JavaScript deve capturar o usuario_id e o veiculo_id atual para criar um novo registro nesta tabela, permitindo o rastreio de quais modelos são mais desejados.

    - id: Identificador único do registro de interesse.

    - usuario_id: Chave estrangeira que vincula o interesse ao cliente (padrão de nomenclatura do JSON Server).

    - veiculo_id: Chave estrangeira que identifica o veículo alvo do interesse.

    - data_registro: Carimbo de data/hora da manifestação de interesse.
 
## 3. Tecnologias e Versões

As versões abaixo foram selecionadas para garantir a estabilidade do sistema e a compatibilidade entre as bibliotecas:

* **Bootstrap v5.3.3**
    * **Importância:** Base do layout responsivo. A versão 5.3 elimina a dependência de jQuery para componentes nativos (como modais e dropdowns), tornando o carregamento do site mais leve e moderno.
* **jQuery v3.7.1 & jQuery Mask v1.14.16**
    * **Importância:** O jQuery facilita a manipulação dinâmica de elementos na tela (DOM). O plugin de máscara é fundamental para garantir que dados sensíveis, como **Telefone** e **CEP**, sejam validados e salvos no formato correto no banco de dados.
* **ViaCEP API v1**
    * **Importância:** API pública real utilizada para automação de endereços. É essencial para cumprir o requisito de integração externa (RA5) e melhorar a usabilidade do formulário de interesse.
* **JSON Server v0.17.4**
    * **Importância:** Atua como nossa "API Fake". É vital para simular a persistência de dados (veículos e leads), permitindo o desenvolvimento de um sistema funcional e dinâmico sem a necessidade de um banco de dados complexo nesta etapa.

---
