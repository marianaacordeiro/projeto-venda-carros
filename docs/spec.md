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
