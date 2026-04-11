# Product Requirements Document (PRD) - Retron

**Autor:** Mariana Cordeiro  
**Projeto:** Retron - Catálogo de Veículos Clássicos  
**Status:** Em Desenvolvimento

## 1. Visão Geral e Objetivo
O **Retron** é uma plataforma web voltada para entusiastas e colecionadores. O sistema resolve a necessidade de uma vitrine digital organizada onde usuários podem explorar um catálogo selecionado de veículos clássicos, acessar detalhes técnicos e manifestar interesse de compra através de um fluxo de cadastro integrado com validação de endereço.

## 2. Atores do Sistema
- **Visitante:** Usuário não autenticado que navega pela Home e visualiza o catálogo.
- **Cliente:** Usuário que preenche o formulário de interesse e fornece dados para contato.
- **O Sistema (Retron):** Ator que processa as validações de campos e busca dados de endereço automaticamente.

## 3. Histórias de Usuário e Escopo

### Épico 1: Cadastro e Localização
- **US01 - Automação de Endereço (CEP):** Como Cliente, quero preencher meu CEP para que Rua, Bairro e Cidade sejam preenchidos automaticamente.
    - **Critérios de Aceitação:** Os campos automáticos devem ser validados antes do envio.
- **US02 - Validação de Contato:** Como Cliente, quero que meus dados de E-mail e Telefone sejam validados para garantir meu cadastro.
    - **Critérios de Aceitação:** O formulário não deve ser enviado se o e-mail for inválido ou o telefone estiver incompleto.

### Épico 2: Gestão de Interesses (Leads)
- **US03 - Registro de Intenção:** Como Cliente, quero clicar em "Tenho Interesse" em um veículo para que minha intenção seja salva no sistema.
    - **Critérios de Aceitação:** O clique deve disparar uma gravação no banco de dados simulado vinculando o cliente ao veículo escolhido.

## 4. Regras de Negócio Principal
- **RN01 - Unicidade:** Um cliente não deve registrar interesse repetido no mesmo veículo.
- **RN02 - Persistência:** Todos os cadastros de interesse devem ser salvos no arquivo de dados (JSON) via script.
