
# Desafio CRUD de Clientes - Java Spring Boot

## Proposta

Este projeto foi proposto pelo professor **Nelio Alves** em seu bootcamp de **Java Spring Boot**. O objetivo da atividade é implementar um **CRUD completo de web services REST** para gerenciar um recurso de **clientes**, contendo as cinco operações básicas:

- **Busca paginada de recursos**
- **Busca de recurso por ID**
- **Inserir um novo recurso**
- **Atualizar um recurso**
- **Deletar um recurso**

## Especificações da Atividade

- O projeto deve ter um ambiente de testes configurado, utilizando um banco de dados **H2**.
- **Maven** deve ser utilizado como gerenciador de dependências.
- A linguagem utilizada é **Java**.

### Requisitos

- É necessário realizar um *seed* no banco de dados com pelo menos **10 clientes** contendo dados significativos (não usar dados fictícios como "Nome 1", "Nome 2", etc.).
  
- **Exceções a serem tratadas**:
  - **Id não encontrado** (para as operações GET por ID, PUT e DELETE) com retorno de código **404**.
  - **Erro de validação** com retorno de código **422** e mensagens customizadas para campos inválidos.

### Regras de Validação

- **Nome** não pode ser vazio.
- **Data de nascimento** não pode ser uma data futura.
- **CPF deve ser unico**.

## Modelo da Classe Client

![Modelo da Classe Client](https://github.com/avbds002/avbds002-desafio-crud-clientes-nelio-alves/assets/169944734/8fc5add7-df47-4218-a5ca-4b1603228da1)

## Testes Manuais no Postman

### 1. **Busca de Cliente por ID**

**GET /clients/{id}**

- **Exemplo**: `GET /clients/1`

### 2. **Busca Paginada de Clientes**

**GET /clients?page=0&size=6&sort=name**

### 3. **Inserção de Novo Cliente**

**POST /clients**

```json
{
  "name": "Maria Silva",
  "cpf": "12345678901",
  "income": 6500.0,
  "birthDate": "1994-07-20",
  "children": 2
}
```

### 4. **Atualização de Cliente**

**PUT /clients/{id}**

```json
{
  "name": "Maria Silvaaa",
  "cpf": "12345678901",
  "income": 6500.0,
  "birthDate": "1994-07-20",
  "children": 2
}
```

### 5. **Deleção de Cliente**

**DELETE /clients/{id}**

## Checklist

1. **Busca por ID**: Retorna o cliente existente.
2. **Busca por ID**: Retorna **404** para cliente inexistente.
3. **Busca Paginada**: Retorna a listagem paginada corretamente.
4. **Inserção de Cliente**: Insere um cliente com dados válidos.
5. **Inserção de Cliente**: Retorna **422** com mensagens customizadas para dados inválidos.
6. **Atualização de Cliente**: Atualiza o cliente com dados válidos.
7. **Atualização de Cliente**: Retorna **404** para cliente inexistente.
8. **Atualização de Cliente**: Retorna **422** com mensagens customizadas para dados inválidos.
9. **Deleção de Cliente**: Deleta o cliente existente.
10. **Deleção de Cliente**: Retorna **404** para cliente inexistente.
