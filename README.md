# Documentação do Programa de Gerenciamento de Biblioteca

## Classes do Programa

### 1. Classe `ItemBiblioteca`
**Descrição:** Esta é uma classe base genérica que representa um item na biblioteca.

**Atributos:**
- `titulo`: Representa o título ou nome do item.

**Métodos:**
- `__init__(self, titulo)`: Construtor que inicializa o atributo `titulo` com o valor fornecido.

**Função no Programa:** Serve como classe base para outros tipos de itens na biblioteca, como livros e usuários.

### 2. Classe `Livro` (Herdeira de `ItemBiblioteca`)
**Descrição:** Esta classe representa um livro na biblioteca e herda da classe `ItemBiblioteca`.

**Atributos:**
- `titulo`: Herdado de `ItemBiblioteca`. Representa o título do livro.
- `autor`: Representa o autor do livro.
- `isbn`: Representa o ISBN (International Standard Book Number) do livro.

**Métodos:**
- `__init__(self, titulo, autor, isbn)`: Construtor que inicializa o `titulo` (usando o construtor da classe base), `autor` e `isbn`.

**Função no Programa:** Representa livros na biblioteca e armazena informações importantes sobre cada livro.

### 3. Classe `Usuario` (Herdeira de `ItemBiblioteca`)
**Descrição:** Esta classe representa um usuário da biblioteca e também herda da classe `ItemBiblioteca`.

**Atributos:**
- `titulo`: Herdado de `ItemBiblioteca`. Aqui, este atributo armazena o nome do usuário (poderia ter sido nomeado mais especificamente como `nome`).
- `matricula`: Representa a matrícula do usuário na biblioteca.

**Métodos:**
- `__init__(self, nome, matricula)`: Construtor que inicializa o `titulo` (nome do usuário) e `matricula`.

**Função no Programa:** Representa os usuários da biblioteca e armazena informações sobre cada usuário.

### 4. Classe `Biblioteca`
**Descrição:** Esta classe gerencia o armazenamento de livros e usuários.

**Atributos:**
- `livros`: Lista que armazena instâncias de objetos `Livro`.
- `usuarios`: Lista que armazena instâncias de objetos `Usuario`.

**Métodos:**
- `__init__(self)`: Construtor que inicializa as listas `livros` e `usuarios` como listas vazias.
- `adicionar_livro(self, livro)`: Método para adicionar um livro na lista de livros.
- `adicionar_usuario(self, usuario)`: Método para adicionar um usuário na lista de usuários.

**Função no Programa:** Serve como um repositório central para armazenar livros e usuários na biblioteca.

### 5. Classe `GerenciadorDePedidos`
**Descrição:** Esta classe gerencia pedidos de empréstimo de livros.

**Atributos:**
- `biblioteca`: Referência à instância da classe `Biblioteca` para acessar livros e usuários.
- `pedidos`: Lista que armazena tuplas contendo (`usuario`, `livro`) que representam os pedidos de empréstimo.

**Métodos:**
- `__init__(self, biblioteca)`: Construtor que inicializa o atributo `biblioteca` e a lista `pedidos`.
- `solicitar_livro(self, usuario, livro)`: Método que adiciona um pedido de empréstimo à lista de pedidos, se o livro estiver disponível na biblioteca. Retorna `True` se o pedido for bem-sucedido, `False` caso contrário.

**Função no Programa:** Gerencia os pedidos de empréstimo de livros feitos pelos usuários.

### 6. Classe `BibliotecaApp`
**Descrição:** Esta classe gerencia a interface gráfica do usuário (GUI) para o sistema da biblioteca, utilizando a biblioteca Tkinter.

**Atributos:**
- `root`: Referência à janela principal do Tkinter.
- `biblioteca`: Instância da classe `Biblioteca`.
- `main_frame`: Frame principal da janela que contém botões para acessar diferentes funcionalidades.

**Métodos:**
- `__init__(self, root)`: Construtor que inicializa a interface gráfica, cria a instância da biblioteca, e adiciona botões de interação.
- `cadastro_livro(self)`: Abre uma tela para cadastrar um novo livro, permitindo que o usuário insira título, autor e ISBN.
- `cadastro_usuario(self)`: Abre uma tela para cadastrar um novo usuário, permitindo que o usuário insira nome e matrícula.
- `visualizar_livros(self)`: Abre uma tela que exibe todos os livros cadastrados.
- `visualizar_usuarios(self)`: Abre uma tela que exibe todos os usuários cadastrados.
- `voltar(self, frame)`: Fecha o frame atual e retorna ao frame principal.

**Função no Programa:** Gerencia a interface gráfica e a interação do usuário com o sistema de biblioteca.

### 7. Bloco Principal
O bloco `if __name__ == "__main__":` é o ponto de entrada do programa. Ele cria uma instância de `BibliotecaApp` e inicia o loop principal do Tkinter para exibir a interface gráfica.
