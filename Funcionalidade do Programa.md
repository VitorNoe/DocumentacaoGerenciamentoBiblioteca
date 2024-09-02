## Funcionalidade do Programa

### 1. Tela Inicial e Interface Principal
Quando o programa é iniciado, ele cria uma janela principal usando o Tkinter, que contém quatro botões que permitem ao usuário navegar para diferentes funcionalidades:

- **Botão "Cadastrar Livro"**: Navega para a tela de cadastro de livros.
- **Botão "Cadastrar Usuário"**: Navega para a tela de cadastro de usuários.
- **Botão "Visualizar Livros"**: Navega para a tela de visualização de todos os livros cadastrados.
- **Botão "Visualizar Usuários"**: Navega para a tela de visualização de todos os usuários cadastrados.

Esses botões são criados dentro de um Frame principal (`main_frame`), que serve como o ponto de partida para todas as outras operações.

### 2. Cadastro de Livros
A funcionalidade de cadastro de livros permite ao usuário adicionar novos livros à biblioteca:

- **Acesso**: Quando o usuário clica no botão "Cadastrar Livro", o método `cadastro_livro()` é chamado.
- **Interface de Cadastro**:
  - A tela principal (`main_frame`) é escondida usando o método `pack_forget()`, e um novo Frame (`cadastro_livro_frame`) é criado para a interface de cadastro.
  - Campos de entrada (`Entry`) e rótulos (`Label`) são criados para inserir as informações do livro: "Título", "Autor" e "ISBN".
- **Salvamento de Dados**:
  - Um botão "Salvar" é criado, que chama a função `salvar_livro()` ao ser clicado.
  - Dentro de `salvar_livro()`, os dados inseridos pelo usuário são recuperados, e uma nova instância de `Livro` é criada.
  - O livro é adicionado à lista de livros da Biblioteca chamando o método `adicionar_livro()`.
  - Após salvar, a tela de cadastro é fechada, e a tela principal é exibida novamente.
- **Voltar para a Tela Principal**:
  - Um botão "Voltar" é fornecido para permitir que o usuário retorne à tela principal sem adicionar um livro. Esse botão chama o método `voltar()` que remove o Frame de cadastro e exibe novamente o `main_frame`.

### 3. Cadastro de Usuários
Esta funcionalidade permite que o usuário adicione novos usuários à biblioteca:

- **Acesso**: Ao clicar no botão "Cadastrar Usuário", o método `cadastro_usuario()` é chamado.
- **Interface de Cadastro**:
  - Similar ao cadastro de livros, a tela principal é escondida, e um novo Frame (`cadastro_usuario_frame`) é criado.
  - Campos de entrada e rótulos são fornecidos para inserir "Nome" e "Matrícula" do usuário.
- **Salvamento de Dados**:
  - Um botão "Salvar" chama a função `salvar_usuario()` ao ser clicado.
  - A função recupera os dados do usuário, cria uma nova instância de `Usuario` e a adiciona à lista de usuários da Biblioteca usando o método `adicionar_usuario()`.
  - Após o salvamento, a tela de cadastro de usuário é fechada, e a tela principal é exibida novamente.
- **Voltar para a Tela Principal**:
  - Assim como na tela de cadastro de livros, um botão "Voltar" permite retornar à tela principal sem salvar um usuário.

### 4. Visualização de Livros
Esta funcionalidade exibe todos os livros cadastrados na biblioteca:

- **Acesso**: Quando o usuário clica no botão "Visualizar Livros", o método `visualizar_livros()` é chamado.
- **Interface de Visualização**:
  - A tela principal é escondida, e um novo Frame (`visualizar_livros_frame`) é criado.
  - Para cada livro na lista de livros (`self.biblioteca.livros`), um rótulo (`Label`) é criado mostrando o título, autor e ISBN do livro.
- **Voltar para a Tela Principal**:
  - Um botão "Voltar" permite ao usuário retornar à tela principal, chamando o método `voltar()`.

### 5. Visualização de Usuários
Esta funcionalidade exibe todos os usuários cadastrados na biblioteca:

- **Acesso**: Ao clicar no botão "Visualizar Usuários", o método `visualizar_usuarios()` é chamado.
- **Interface de Visualização**:
  - A tela principal é escondida, e um novo Frame (`visualizar_usuarios_frame`) é criado.
  - Para cada usuário na lista de usuários (`self.biblioteca.usuarios`), um rótulo (`Label`) é criado mostrando o nome e a matrícula do usuário.
  - Nota: O código reutiliza o atributo `titulo` herdado da classe base `ItemBiblioteca` para armazenar o nome do usuário, o que pode ser confuso.
- **Voltar para a Tela Principal**:
  - Assim como nas outras telas de visualização, um botão "Voltar" é fornecido para retornar à tela principal.

### 6. Navegação entre Telas
O método `voltar()` é usado para esconder o frame atual e mostrar o frame principal. Ele é chamado sempre que o usuário clica no botão "Voltar" em qualquer tela de cadastro ou visualização.

A navegação entre telas é feita escondendo o frame atual com `pack_forget()` e mostrando o frame desejado com `pack()`.
