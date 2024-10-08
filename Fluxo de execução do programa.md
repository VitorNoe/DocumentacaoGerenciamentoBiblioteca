```markdown
## Fluxo de Execução do Programa

### 1. Inicialização do Programa
O ponto de entrada do programa é o bloco condicional `if __name__ == "__main__":`. Quando o programa é executado, o proximo comando é iniciado:

```python
if __name__ == "__main__":
    root = tk.Tk()  # Cria a janela principal do Tkinter.
    app = BibliotecaApp(root)  # Cria uma instância da classe BibliotecaApp, passando a janela principal.
    root.mainloop()  # Inicia o loop principal do Tkinter, mantendo a janela aberta e respondendo a eventos.
```

- **`tk.Tk()`**: Cria a janela principal da aplicação.
- **`BibliotecaApp(root)`**: Instancia a classe `BibliotecaApp`, que inicializa a interface gráfica da aplicação.
- **`root.mainloop()`**: Inicia o loop de eventos do Tkinter, que mantém a aplicação em execução e aguarda a interação do usuário.

### 2. Criação da Instância `BibliotecaApp`
Quando a instância `BibliotecaApp` é criada, o método `__init__()` da classe `BibliotecaApp` é executado:

- **`self.root = root`**: A janela principal do Tkinter é armazenada no atributo `self.root`.
- **`self.biblioteca = Biblioteca()`**: Uma instância da classe `Biblioteca` é criada e atribuída a `self.biblioteca`. Essa instância gerencia a lista de livros e usuários.
- **`self.main_frame = tk.Frame(root)`**: Cria um frame principal para conter os botões de funcionalidade.

**Botões de Navegação**:
- Os botões para "Cadastrar Livro", "Cadastrar Usuário", "Visualizar Livros" e "Visualizar Usuários" são criados e adicionados ao `main_frame` com as funções de comando apropriadas para cada ação:
  - Botão "Cadastrar Livro": Chama `self.cadastro_livro`.
  - Botão "Cadastrar Usuário": Chama `self.cadastro_usuario`.
  - Botão "Visualizar Livros": Chama `self.visualizar_livros`.
  - Botão "Visualizar Usuários": Chama `self.visualizar_usuarios`.
- **Exibição do Frame Principal**: `self.main_frame.pack()` exibe o frame principal na janela.

### 3. Fluxo de Cadastro de Livro
Quando o usuário clica no botão "Cadastrar Livro", o método `cadastro_livro()` é chamado:

- **`self.main_frame.pack_forget()`**: O frame principal é escondido.
- **Criação de `cadastro_livro_frame`**: Um novo frame para o cadastro de livros é criado.

**Campos de Entrada e Botões**:
- Campos de entrada para "Título", "Autor" e "ISBN" são criados.
- **Botão "Salvar"**: Chama a função `salvar_livro()` ao ser clicado.
- **Botão "Voltar"**: Chama `self.voltar(cadastro_livro_frame)` para voltar ao `main_frame`.

**Salvamento de Livro (`salvar_livro()`)**:
- Recupera os dados dos campos de entrada.
- Cria uma nova instância de `Livro` com os dados inseridos.
- Chama `self.biblioteca.adicionar_livro(novo_livro)` para adicionar o livro à biblioteca.
- Esconde o frame de cadastro e exibe o `main_frame`.

### 4. Fluxo de Cadastro de Usuário
Quando o usuário clica no botão "Cadastrar Usuário", o método `cadastro_usuario()` é chamado:

- **`self.main_frame.pack_forget()`**: O frame principal é escondido.
- **Criação de `cadastro_usuario_frame`**: Um novo frame para o cadastro de usuários é criado.

**Campos de Entrada e Botões**:
- Campos de entrada para "Nome" e "Matrícula" são criados.
- **Botão "Salvar"**: Chama a função `salvar_usuario()` ao ser clicado.
- **Botão "Voltar"**: Chama `self.voltar(cadastro_usuario_frame)` para voltar ao `main_frame`.

**Salvamento de Usuário (`salvar_usuario()`)**:
- Recupera os dados dos campos de entrada.
- Cria uma nova instância de `Usuario` com os dados inseridos.
- Chama `self.biblioteca.adicionar_usuario(novo_usuario)` para adicionar o usuário à biblioteca.
- Esconde o frame de cadastro e exibe o `main_frame`.

### 5. Fluxo de Visualização de Livros
Quando o usuário clica no botão "Visualizar Livros", o método `visualizar_livros()` é chamado:

- **`self.main_frame.pack_forget()`**: O frame principal é escondido.
- **Criação de `visualizar_livros_frame`**: Um novo frame para a visualização dos livros é criado.

**Exibição dos Livros**:
- Itera sobre a lista `self.biblioteca.livros` e cria um rótulo (`Label`) para cada livro, mostrando o título, autor e ISBN.
- **Botão "Voltar"**: Um botão "Voltar" é criado para retornar à tela principal, chamando `self.voltar(visualizar_livros_frame)`.

### 6. Fluxo de Visualização de Usuários
Quando o usuário clica no botão "Visualizar Usuários", o método `visualizar_usuarios()` é chamado:

- **`self.main_frame.pack_forget()`**: O frame principal é escondido.
- **Criação de `visualizar_usuarios_frame`**: Um novo frame para a visualização dos usuários é criado.

**Exibição dos Usuários**:
- Itera sobre a lista `self.biblioteca.usuarios` e cria um rótulo (`Label`) para cada usuário, mostrando o nome (armazenado em `titulo`) e matrícula.
- **Botão "Voltar"**: Um botão "Voltar" é criado para retornar à tela principal, chamando `self.voltar(visualizar_usuarios_frame)`.

### 7. Fluxo de Voltar para a Tela Principal
O método `voltar(frame)` é um utilitário para retornar ao frame principal:

- **Esconde o Frame Atual**: `frame.pack_forget()` esconde o frame atual.
- **Exibe o Frame Principal**: `self.main_frame.pack()` exibe o frame principal novamente.
