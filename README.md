# 🚀 Apresentação Técnica: Sistema CRUD & Autenticação (Projeto Gabi)
**Curso:** Técnico em Desenvolvimento de Sistemas - ETEC  
**Estudante:** Donizete dos Santos (`donigemini`)  
**Disciplina:** Desenvolvimento de Sistemas II - Agenda 08  

---

## 📌 Visão Geral do Projeto
Apresentação técnica do projeto de **Cadastro de Amigos (CRUD)** com **Sistema de Login e Autenticação de Usuários**, desenvolvido em PHP, HTML5, W3.CSS e banco de dados MySQL via extensão PDO.

---

## 🛠️ Arquitetura do Sistema
* **Front-End:** HTML5 / W3.CSS (Interface responsiva e formulários).
* **Back-End:** PHP 8 (Lógica de negócios, controle de sessões e rotas).
* **Banco de Dados:** MySQL (Persistência dos dados de usuários e contatos).
* **Servidor Local:** XAMPP / Apache (`http://localhost/`).

---

## 🔐 1. Módulo de Autenticação (Login & Segurança)
* **Validação via Formulário:** Método `POST` enviando credenciais de acesso.
* **Controle de Sessão (`session_start()`):**
  * Criação da sessão `$_SESSION['usuario']` após autenticação bem-sucedida.
  * Proteção do cabeçalho das páginas restritas (redireciona para o `login.php` caso não haja sessão ativa).
* **Logout (`logout.php`):** Encerramento seguro da sessão via `session_destroy()`.

---

## ⚙️ 2. Módulo CRUD (Gestão de Amigos)

O sistema realiza as quatro operações fundamentais no banco de dados:

1. **[ C ] Create (Cadastrar):** Formulário de inserção executando `INSERT INTO` via PDO com *Prepared Statements* para prevenir SQL Injection.
2. **[ R ] Read (Listar/Buscar):** Consulta `SELECT` renderizando dinamicamente a tabela de contatos com filtro de busca.
3. **[ U ] Update (Editar):** Recuperação dos dados do registro pelo `ID` e atualização via `UPDATE`.
4. **[ D ] Delete (Excluir):** Remoção de registro pelo `ID` com confirmação previa.

---

## 📂 Estrutura de Arquivos do Projeto
```text
├── includes/
│   ├── conexao.php          # Conexão PDO com MySQL
│   ├── header.php           # Cabeçalho da página
│   └── footer.php           # Rodapé da página
├── index.php                # Painel principal / Listagem de amigos
├── login.php                # Tela de autenticação
├── logout.php               # Encerramento de sessão
├── cadastrar.php            # Inserção de novos amigos
├── editar.php               # Edição de registros
└── excluir.php              # Exclusão de registros
