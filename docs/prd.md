# Product Requirements Document (PRD) - Retron

**Autor:** Mariana Cordeiro  
**Projeto:** Retron - Catálogo de Veículos Clássicos  
**Status:** Em Desenvolvimento

## 1. Visão Geral e Objetivo
O **Retron** é uma plataforma web didática projetada para entusiastas de carros vintage. O objetivo é oferecer uma vitrine digital onde o usuário possa explorar veículos históricos e registrar interesse de compra. O diferencial do sistema é a automação de dados (ViaCEP) e a persistência de intenções de compra em um banco de dados simulado.

## 2. Atores do Sistema
- **Visitante:** Usuário não autenticado que explora o catálogo e o carrossel.
- **Cliente:** Usuário autenticado que pode registrar interesse e salvar dados de contato.
- **Sistema (Retron):** Gerencia as validações de endereço e armazena os leads de venda.

## 3. Histórias de Usuário e Escopo

### Épico 1: Experiência e Interface (UX/UI)
- **US01 - Carrossel de Destaques:** Como Visitante, quero visualizar um carrossel de fotos na Home para conhecer os modelos principais.
    - **Critério de Aceitação:** O carrossel deve transitar automaticamente e permitir navegação manual.
- **US02 - Responsividade:** Como Visitante, quero acessar o site por dispositivos móveis sem perda de funcionalidade.
    - **Critério de Aceitação:** O layout deve se adaptar para resoluções de celular e tablet.

### Épico 2: Jornada do Cliente e Cadastro
- **US03 - Preenchimento de CEP:** Como Cliente, quero preencher meu CEP para que meu endereço seja completado automaticamente.
    - **Critério de Aceitação:** Integração com API ViaCEP; preenchimento automático de Rua, Bairro e Cidade.
- **US04 - Validação de Contato:** Como Cliente, quero que meus dados sejam validados para garantir que a loja consiga me contatar.
    - **Critério de Aceitação:** E-mail deve conter "@"; Telefone deve seguir formato válido.

### Épico 3: Conversão e Leads
- **US05 - Registro de Interesse:** Como Cliente, quero clicar em "Tenho Interesse" para salvar minha intenção de compra.
    - **Critério de Aceitação:** O registro deve ser salvo no `db.json` vinculado ao ID do usuário e do veículo.

## 4. Regras de Negócio Principal
- **RN01 - Unicidade:** Um cliente só pode registrar interesse uma única vez por veículo.
- **RN02 - Persistência:** Todas as alterações de cadastro e interesse devem ser refletidas no JSON Server imediatamente.
