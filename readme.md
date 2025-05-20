# pge-ecommerce
Aula sobre como criar uma página que adiciona produtos de E-commerce.

![CREATE SQL DATABASE](https://github.com/user-attachments/assets/4bc4975b-4030-4079-b484-2a2b069c4a18)
import sqlite3

# Conectar ao banco de dados (ou criar um novo)
conn = sqlite3.connect("produtos.db")
cursor = conn.cursor()

# Criar tabela se não existir
cursor.execute("""
CREATE TABLE IF NOT EXISTS produtos (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT NOT NULL,
    preco REAL NOT NULL,
    estoque INTEGER NOT NULL
)
""")

# Função para adicionar produto
def adicionar_produto(nome, preco, estoque):
    cursor.execute("INSERT INTO produtos (nome, preco, estoque) VALUES (?, ?, ?)", (nome, preco, estoque))
    conn.commit()
    print(f"Produto '{nome}' adicionado com sucesso!")

# Exemplo de uso
adicionar_produto("Notebook", 3500.00, 10)
adicionar_produto("Mouse", 150.00, 50)
# Fechar conexão
conn.close()

![Criando tabela produtos E-commerce](https://github.com/user-attachments/assets/f17a163b-dc64-4bf1-ae97-b3d30c7178b4)

A inclusão em sql de como criar uma tabela sem a necessidade de uma base de dados externa para adicionar produtos na página é mais prático. 
-- Criar banco de dados em SQLite e tabela de produtos
CREATE TABLE IF NOT EXISTS produtos (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT NOT NULL,
    preco REAL NOT NULL,
    estoque INTEGER NOT NULL
);

-- Inserir alguns produtos como exemplo
INSERT INTO produtos (nome, preco, estoque) VALUES 
('Notebook', 3500.00, 10),
('Mouse', 150.00, 50),
('Teclado', 200.00, 30);

![Pág result final projeto E-commerce](https://github.com/user-attachments/assets/5dc59c8d-99c3-4ee2-a9a9-eeb5d09c1eac)

Top demais a inserção de todos os campos necessários aliando o código fonte final e incluindo imagens com IA . Valeu por tudo Henrique!
