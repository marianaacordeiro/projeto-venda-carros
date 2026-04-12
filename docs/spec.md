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
