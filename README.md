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

## Resumo
Este programa fornece uma interface gráfica simples para o gerenciamento de uma biblioteca, onde é possível cadastrar livros, cadastrar usuários, visualizar os livros e usuários cadastrados e gerenciar pedidos de empréstimo. Cada classe tem um propósito claro e está bem organizada para representar os diferentes aspectos do sistema de biblioteca.


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

## Resumo
O programa oferece uma interface gráfica intuitiva para gerenciar livros e usuários de uma biblioteca. As funcionalidades principais são o cadastro e visualização de livros e usuários, e a navegação entre as telas é facilitada por botões de "Voltar". A arquitetura do programa permite fácil expansão para incluir mais funcionalidades no futuro, como a implementação de empréstimos e devoluções de livros.





### Manual de Instalação e Uso

Este manual fornece instruções sobre como instalar e usar o programa de gerenciamento de biblioteca com interface gráfica desenvolvida com Python e Tkinter.

---

### 1. **Dependências Necessárias**

Para executar o programa, as seguintes dependências são necessárias:

- **Python 3.x**: O programa foi desenvolvido em Python, portanto, é necessário ter o Python instalado no sistema.
- **Tkinter**: Biblioteca padrão do Python para a criação de interfaces gráficas (GUI).

> **Nota:** O Tkinter já vem incluído na instalação padrão do Python em sistemas operacionais como Windows, Linux e macOS.

### 2. **Instalação das Dependências**

#### Verificar Instalação do Python e Tkinter

Antes de instalar as dependências, certifique-se de que o Python e o Tkinter estão instalados:

1. **Verificar a instalação do Python:**
   Abra o terminal ou prompt de comando e execute o comando:

   ```bash
   python --version
   ```
   
   ou

   ```bash
   python3 --version
   ```

   Se o Python estiver instalado, o número da versão será exibido. Por exemplo, `Python 3.8.10`.

2. **Verificar a instalação do Tkinter:**
   Você pode verificar se o Tkinter está instalado executando o seguinte comando no terminal:

   ```bash
   python -m tkinter
   ```
   
   ou

   ```bash
   python3 -m tkinter
   ```

   Isso abrirá uma janela de demonstração do Tkinter se ele estiver instalado corretamente.

#### Instalação de Outras Dependências (Opcional)

Se, por algum motivo, outras dependências forem necessárias ou desejadas para expandir o programa (como pandas para manipulação de dados), elas podem ser instaladas usando o `pip`.

Exemplo de instalação de dependências adicionais (não necessárias para o programa atual):

```bash
pip install pandas
```

ou

```bash
pip3 install pandas
```

### 3. **Inicialização do Programa**

Depois de garantir que o Python e o Tkinter estão instalados, você pode iniciar o programa seguindo estas etapas:

1. **Baixar ou Clonar o Código Fonte**:
   - Baixe ou clone o código-fonte do programa para o seu computador. Suponha que o arquivo seja chamado `biblioteca.py`.

2. **Navegar até o Diretório do Programa**:
   Abra o terminal (ou prompt de comando) e navegue até o diretório onde o arquivo `biblioteca.py` está localizado:

   ```bash
   cd caminho/para/o/diretorio
   ```

3. **Executar o Programa**:
   Execute o programa usando o Python:

   ```bash
   python biblioteca.py
   ```

   ou

   ```bash
   python3 biblioteca.py
   ```

Se o Python estiver configurado corretamente no PATH, a janela principal do programa será aberta.

### 4. **Guia de Uso do Programa**

Uma vez que o programa está em execução, o usuário verá a interface gráfica principal com várias opções:

#### **Tela Principal**

- A tela principal contém quatro botões:
  - **Cadastrar Livro**: Leva à tela de cadastro de livros.
  - **Cadastrar Usuário**: Leva à tela de cadastro de usuários.
  - **Visualizar Livros**: Mostra uma lista de todos os livros cadastrados na biblioteca.
  - **Visualizar Usuários**: Mostra uma lista de todos os usuários cadastrados.

#### **Cadastro de Livros**

1. **Clique no botão "Cadastrar Livro"**.
2. Preencha os campos de **Título**, **Autor** e **ISBN** do livro.
3. Clique no botão **Salvar** para adicionar o livro à biblioteca.
4. Para retornar à tela principal sem salvar, clique no botão **Voltar**.

#### **Cadastro de Usuários**

1. **Clique no botão "Cadastrar Usuário"**.
2. Preencha os campos de **Nome** e **Matrícula** do usuário.
3. Clique no botão **Salvar** para adicionar o usuário à biblioteca.
4. Para retornar à tela principal sem salvar, clique no botão **Voltar**.

#### **Visualização de Livros**

1. **Clique no botão "Visualizar Livros"**.
2. Uma nova tela será exibida com a lista de todos os livros cadastrados, mostrando o **Título**, **Autor** e **ISBN**.
3. Clique no botão **Voltar** para retornar à tela principal.

#### **Visualização de Usuários**

1. **Clique no botão "Visualizar Usuários"**.
2. Uma nova tela será exibida com a lista de todos os usuários cadastrados, mostrando o **Nome** e **Matrícula**.
3. Clique no botão **Voltar** para retornar à tela principal.

### 5. **Conclusão**

Este programa oferece uma interface simples e intuitiva para o gerenciamento de livros e usuários de uma biblioteca. As funcionalidades principais incluem o cadastro de novos livros e usuários e a visualização dos itens cadastrados. 

Seguindo este manual, você deverá ser capaz de instalar, configurar e usar o programa facilmente. Caso precise de funcionalidades adicionais ou queira personalizar o programa, o código é modular e pode ser expandido conforme necessário.
