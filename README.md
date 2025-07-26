# FakePinterest

### Descrição
Um clone simplificado da plataforma Pinterest, desenvolvido como um projeto de estudo para aplicar conceitos de desenvolvimento web com Python e o framework Flask. A aplicação permite que usuários criem contas, façam login, visualizem um feed de imagens e publiquem suas próprias fotos em seus perfis. Desenvolvido com base no projeto do curso da Hashtag Programação.

### Tecnologias Utilizadas
- **Backend**:
  - **Python**: Linguagem de programação principal.
  - **Flask**: Framework web para a construção da aplicação.
  - **Flask-SQLAlchemy**: ORM para interagir com o banco de dados.
  - **Flask-Login**: Gerenciamento de sessões de usuário (login, logout).
  - **Flask-Bcrypt**: Hashing de senhas para segurança.
  - **Flask-WTF**: Criação e validação de formulários.
- **Frontend**:
  - **HTML5**: Estrutura das páginas.
  - **CSS3**: Estilização.
  - **Bootstrap**: Framework CSS para agilizar o design responsivo.
- **Banco de Dados**:
  - **SQLite**: Banco de dados relacional leve e baseado em arquivo.

### Estrutura do Projeto
```
FakePinterest/
├── fakepinterest/
│   ├── __init__.py       # Inicializa a aplicação Flask e suas extensões.
│   ├── models.py         # Define os modelos do banco de dados (Usuario, Foto).
│   ├── forms.py          # Contém os formulários WTForms para login, cadastro e upload.
│   ├── routes.py         # Controla as rotas e a lógica de cada página.
│   ├── static/           # Armazena arquivos estáticos (CSS, JS, imagens de layout).
│   │   └── fotos_posts/  # Diretório para as imagens enviadas pelos usuários.
│   └── templates/        # Arquivos HTML com a estrutura das páginas (Jinja2).
├── instance/
│   └── comunidade.db     # Arquivo do banco de dados SQLite (gerado automaticamente).
├── criar_banco.py        # Script para criar as tabelas no banco de dados.
├── main.py               # Ponto de entrada para executar a aplicação.
├── requirements.txt      # Lista de dependências do projeto.
└── README.md             # Documentação do projeto.
```

### Como Funciona
A aplicação segue a arquitetura padrão de um projeto Flask:
1.  **`main.py`**: É o ponto de entrada que inicia o servidor de desenvolvimento do Flask.
2.  **`fakepinterest/__init__.py`**: Cria a instância da aplicação Flask, carrega as configurações (como a chave secreta e o caminho do banco de dados) e inicializa as extensões (SQLAlchemy, Bcrypt, LoginManager).
3.  **`fakepinterest/models.py`**: Define as tabelas `Usuario` e `Foto` como classes Python, mapeando-as para o banco de dados.
4.  **`fakepinterest/routes.py`**: Mapeia as URLs (rotas) para funções Python (views). Essas funções processam as requisições, interagem com o banco de dados através dos modelos e renderizam os templates HTML para o usuário.
5.  **`fakepinterest/forms.py`**: Define as classes de formulário para garantir a validação e a segurança dos dados enviados pelos usuários (ex: login, cadastro).

### Funcionalidades
- ✅ **Autenticação de Usuários**: Sistema completo de cadastro, login e logout.
- ✅ **Feed de Fotos**: Página inicial que exibe as postagens de todos os usuários.
- ✅ **Perfil de Usuário**: Página de perfil que exibe todas as fotos postadas por um usuário específico.
- ✅ **Upload de Fotos**: Usuários autenticados podem enviar novas imagens para a plataforma.
- ✅ **Segurança**: Senhas armazenadas de forma segura usando hashing.

### Como Usar
Siga os passos abaixo para configurar e rodar o projeto localmente.

1.  **Clone o repositório**
   ```bash
   git clone https://github.com/HassanPls/FakePinterest.git
   cd FakePinterest
   ```

2.  **Crie e ative um ambiente virtual**
    ```bash
    # Criar o ambiente
    python -m venv .venv
 
    # Ativar no Windows
    .venv\Scripts\activate
 
    # Ativar no Linux/macOS
    source .venv/bin/activate
    ```

3.  **Instale as dependências**
    (Certifique-se de que o arquivo `requirements.txt` existe na raiz do projeto)
    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure a Chave Secreta**
    A aplicação precisa de uma chave secreta para funcionar. Você pode gerar uma nova com o script `secret.py` ou usar a que já está no código.
    ```bash
    python secret.py
    ```
    Copie a chave gerada e, se desejar, substitua a existente na variável `app.config["SECRET_KEY"]` no arquivo `fakepinterest/__init__.py`.

5.  **Crie o Banco de Dados**
    Execute o script `criar_banco.py` para inicializar o banco de dados SQLite e criar as tabelas.
    ```bash
    python criar_banco.py
    ```
    Isso criará o arquivo `instance/comunidade.db`.

6.  **Inicie a aplicação**
    Com tudo configurado, rode o `main.py` para iniciar o servidor.
    ```bash
    python main.py
    ```

7.  **Acesse no navegador**
    Abra seu navegador e acesse: `http://127.0.0.1:5000`

### **Contribuições**

Contribuições são bem-vindas! Se você encontrar algum problema ou tiver sugestões de melhoria, por favor, abra um issue ou faça um pull request.

### **Licença**

Este projeto está licenciado sob a licença [MIT](https://opensource.org/licenses/MIT).