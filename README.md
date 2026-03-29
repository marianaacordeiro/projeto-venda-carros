# 🏎️ Retron - Catálogo de Veículos Clássicos

**Autor:** Mariana Nicolle Cordeiro

Este projeto tem como objetivo implementar progressivamente uma aplicação web voltada para a exibição e intermediação de venda de veículos (foco em carros clássicos e retrô). O **Retron** oferece uma interface moderna para que entusiastas naveguem por um catálogo selecionado, realizem cadastros com validação automática de endereço e manifestem interesse em modelos específicos.

O frontend da aplicação foi desenvolvido com **HTML, CSS (Sass) e JavaScript**, e o backend é simulado por uma **API Fake**, utilizando o **JSON Server**.

---

## 📚 Documentação do Projeto

Para entender as regras de negócio, o escopo e a arquitetura técnica da aplicação, consulte os documentos abaixo:

- 📄 [Product Requirements Document (PRD)](docs/prd.md) – Visão geral, atores e histórias de usuário.
- 🛠️ [Especificação Técnica (Tech Spec)](docs/spec.md) – Diagrama de banco de dados (DER) e rotas da API.

---

## 🎨 Design

- 🎨 [Design System](https://stitch.withgoogle.com/u/1/projects/17515904052542787954?pli=1) – Identidade visual (Cores, Tipografia e Componentes).
- 🖼️ [Protótipo no Stitch](https://stitch.withgoogle.com/u/1/projects/17515904052542787954?pli=1) – Telas interativas da aplicação (Mobile e Desktop).

---

## 💻 Tecnologias e Dependências

- **Framework CSS:** [Bootstrap 5](https://getbootstrap.com/)
- **JavaScript:**
  - [jQuery](https://jquery.com/) – Para animações e manipulação dinâmica do DOM.
  - [jQuery Mask Plugin](https://igoresobarboza.github.io/jquery-mask-plugin/) – Para máscaras de formulário (CPF, CEP, Telefone).
- **API:**
  - [JSON Server](https://github.com/typicode/json-server) – Para simular uma API REST de veículos e interessados.
  - [ViaCEP](https://viacep.com.br/) – API pública para preenchimento automático de endereço.

---

## ✅ Checklist | Indicadores de Desempenho (ID)

### RA1 - Frameworks CSS e Layouts Responsivos

- [ ] **ID 01** - Prototipa interfaces adaptáveis (Figma).
- [ ] **ID 02** - Implementa layout responsivo com Bootstrap usando Flexbox/Grid.
- [ ] **ID 03** - Implementa layout responsivo com CSS puro (Flexbox/Grid).
- [ ] **ID 04** - Utiliza componentes prontos do Framework (Cards, Carousel, Navbar).
- [ ] **ID 05** - Cria layout fluido usando unidades relativas (vw, vh, %, rem).
- [ ] **ID 06** - Aplica um Design System consistente em toda a aplicação.
- [ ] **ID 07** - Utiliza Sass (SCSS) com variáveis e mixins para modularizar o código.
- [ ] **ID 08** - Aplica tipografia responsiva ou fluida.
- [ ] **ID 09** - Aplica técnicas de responsividade de imagens (object-fit).
- [ ] **ID 10** - Otimiza imagens (WebP) e carregamento adaptativo.

### RA2 - Formulários e Validações

- [ ] **ID 11** - Implementa validação HTML nativa com mensagens de erro.
- [ ] **ID 12** - Aplica expressões regulares (REGEX) para validações customizadas.
- [ ] **ID 13** - Utiliza elementos de seleção (checkbox, radio, select).
- [ ] **ID 14** - Implementa leitura e escrita no Web Storage (localStorage).

### RA3 - Ferramentas de Desenvolvimento

- [ ] **ID 15** - Configura ambiente com Node.js e NPM.
- [ ] **ID 16** - Utiliza boas práticas de versionamento no Git/GitHub (commits semânticos, .gitignore).
- [ ] **ID 17** - Mantém um README.md padronizado com checklist preenchido.
- [ ] **ID 18** - Organiza arquivos do projeto de forma modular.
- [ ] **ID 19** - Configura linters e formatadores (ESLint, Prettier).

### RA4 - Bibliotecas e Interatividade

- [ ] **ID 20** - Utiliza jQuery para manipulação do DOM e interatividade.
- [ ] **ID 21** - Integra e configura um plugin jQuery (jQuery Mask).

### RA5 - Requisições Assíncronas (APIs)

- [ ] **ID 22** - Realiza requisições para API fake para persistir dados de formulário.
- [ ] **ID 23** - Realiza requisições para API fake para exibir dados na página.
- [ ] **ID 24** - Realiza requisições para APIs públicas reais (ViaCEP).
