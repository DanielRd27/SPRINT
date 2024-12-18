# Sistema de cadastro de fornecedor e produto

### Criaçao do Banco de dados
```sql

CREATE DATABASE sistema CHARACTER SET utf8mb4;

```

<!-- ___________________________________________ -->

### Criar tabela usuarios
```sql

-- Expressão SQL para criar a tabela de usuários
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50) NOT NULL,
    senha VARCHAR(255) NOT NULL
);

```

<!-- ___________________________________________ -->

### Criar tabela fornecedores
```sql

-- Expressão SQL para criar a tabela de fornecedores
CREATE TABLE fornecedores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100),
    telefone VARCHAR(20)
    endereco VARCHAR(255),
    cnpj VARCHAR(20),
    observacoes TEXT
);

``` 

<!-- ___________________________________________ -->

### Criar tabela produtos
```sql

-- Expressão SQL para criar a tabela de produtos relacionada via FK com a tabela de fornecedores
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    fornecedor_id INT,
    nome VARCHAR(100) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10, 2) NOT NULL,
    codigo VARCHAR(100) NOT NULL,
    quantidade INT NOT NULL,
    FOREIGN KEY (fornecedor_id) REFERENCES fornecedores(id)
);

``` 

### Criar conta para Admin e Ceo

```sql

INSERT INTO usuarios (usuario, senha) VALUES ('Adm', MD5('Admn2627'));

INSERT INTO usuarios (usuario, senha) VALUES ('Ceo', MD5('Ceo2627'));

```

