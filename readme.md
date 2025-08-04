# 🛠️ Esquema Conceitual - Oficina Mecânica

Este projeto representa um **modelo conceitual de banco de dados** para um sistema de controle e gerenciamento de **ordens de serviço** de uma oficina mecânica, conforme o desafio proposto na plataforma **DIO**.

## 📖 Narrativa

Clientes levam veículos à oficina para conserto ou revisões. Cada veículo é designado a uma equipe de mecânicos, que identifica os serviços e preenche uma ordem de serviço (OS), com data de emissão, status, e valor total (considerando mão de obra e peças). O cliente autoriza a execução dos serviços, que são avaliados e realizados pela mesma equipe.

## 🧱 Entidades e Relacionamentos

### 🔹 Cliente
- `id_cliente` (PK)
- `nome`
- `endereco`
- `telefone`

### 🔹 Veículo
- `id_veiculo` (PK)
- `modelo`
- `placa`
- `id_cliente` (FK)

### 🔹 Mecânico
- `id_mecanico` (PK)
- `nome`
- `endereco`
- `especialidade`

### 🔹 Equipe
- `id_equipe` (PK)
- `nome`

### 🔹 EquipeMecanico (Relacionamento N:N)
- `id_equipe` (FK)
- `id_mecanico` (FK)

### 🔹 Ordem de Serviço (OS)
- `id_os` (PK)
- `data_emissao`
- `data_conclusao`
- `status`
- `valor_total`
- `id_veiculo` (FK)
- `id_equipe` (FK)

### 🔹 Serviço
- `id_servico` (PK)
- `descricao`
- `valor_mao_obra`

### 🔹 Peça
- `id_peca` (PK)
- `nome`
- `valor`

### 🔹 OSServico (Relacionamento N:N entre OS e Serviço)
- `id_os` (FK)
- `id_servico` (FK)

### 🔹 ServicoPeca (Relacionamento N:N entre Serviço e Peça)
- `id_servico` (FK)
- `id_peca` (FK)

---

## 🖼️ Diagrama Conceitual (ER)

O diagrama abaixo representa visualmente todas as entidades e seus relacionamentos:

![Diagrama Conceitual](esquema_oficina.png)

---

## 🚀 Como Utilizar

1. Clone este repositório.
2. Abra o arquivo `esquema_oficina.png` para visualizar o modelo.
3. Utilize o script SQL (opcional) para implementar o banco no MySQL.
4. Caso deseje evoluir o projeto, você pode criar as versões **lógica** e **física** do modelo.

---

## 📌 Tecnologias Utilizadas

- [MySQL Workbench](https://www.mysql.com/products/workbench/)
- [Graphviz](https://graphviz.org/) (para geração do diagrama)
- Markdown (`README.md`)

---

## ✍️ Autor

Projeto desenvolvido por **Gerson Junior** como parte de desafio prático na plataforma DIO.

---

## 📎 Licença

Este projeto está licenciado sob a licença MIT.

