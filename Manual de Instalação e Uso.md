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
