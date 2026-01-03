# Projeto Agenda de Contatos

Projeto de uma agenda de contatos desenvolvido com a finalidade de estudar o framework Django. Como o objetivo inclui o deploy (publicação) da aplicação em um servidor, a SECRET_KEY` foi removida por segurança. Caso deseje rodar a aplicação localmente, siga as instruções de configuração no final deste documento.

---

## 🎯 Funcionalidades

- **Tabela com os Contatos da Agenda**
- **Criação de Contatos**
- **Página de Login**
- **Página de Criação de Conta**
- **Página de Edição de Conta**
- **Edição e Exclusão de Contato (somente para quem criou o contato, ou seja, o proprietário do contato na agenda)**
- **Paginação e Pesquisa de Contatos**

---

## 🛠️ Tecnologias

- **Django 6**
- **HTML e CSS**

---

## 🚀 Como Rodar a Aplicação

### Passo a Passo

#### 1️⃣ Clone o repositório

```bash
git clone https://github.com/joserodrigues27/projeto-agenda-django.git
cd projeto-agenda-django
```

#### 2️⃣ Crie e ative um ambiente virtual

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows
```

#### 3️⃣ Instale as dependências

```bash
pip install -r requirements.txt
```

#### 4️⃣ Configure as variáveis de ambiente

1. Crie o arquivo `.env` baseado no exemplo:
```bash
cp .env.example .env  # Linux/Mac
# ou
copy .env.example .env  # Windows
```

2. Gere e grave a `SECRET_KEY` no arquivo `.env`:

```bash
python -c "from django.core.management.utils import get_random_secret_key; print(f'SECRET_KEY={get_random_secret_key()}')" >> .env
```

- **Nota:** Este comando adiciona a chave gerada automaticamente ao final do seu arquivo .env`.

#### 5️⃣ Configure o banco de dados

```bash
python manage.py makemigrations
python manage.py migrate
```

#### 6️⃣ Crie um superusuário (para acessar a área admin)

```bash
python manage.py createsuperuser
```

#### 7️⃣ Execute o servidor

```bash
python manage.py runserver
```

#### 8️⃣ Acesse a aplicação

- **Agenda de Contatos:** `http://localhost:8000`
- **Visualização de Contato:** `http://localhost:8000/contact/id`
- **Login:** `http://localhost:8000/user/login`
- **Criar/Registrar uma Conta Nova:** `http://localhost:8000/user/create`
- **Logout:** `http://localhost:8000/user/logout` (requer login)
- **Edição de Conta:** `http://localhost:8000/user/update` (requer login)
- **Criação de Contatos:** `http://localhost:8000/contact/create` (requer login)
- **Edição de Contato:** `http://localhost:8000/contact/id/update` (requer login)
- **Exclusão de Contato:** `http://localhost:8000/contact/id/delete` (requer login)

