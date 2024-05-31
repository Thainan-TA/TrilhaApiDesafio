# DIO - Trilha .NET - API e Entity Framework
www.dio.me

## Desafio de projeto
Para este desafio, você precisará usar seus conhecimentos adquiridos no módulo de API e Entity Framework, da trilha .NET da DIO.

## Contexto
Você precisa construir um sistema gerenciador de tarefas, onde você poderá cadastrar uma lista de tarefas que permitirá organizar melhor a sua rotina.

Essa lista de tarefas precisa ter um CRUD, ou seja, deverá permitir a você obter os registros, criar, salvar e deletar esses registros.

A sua aplicação deverá ser do tipo Web API ou MVC, fique a vontade para implementar a solução que achar mais adequado.

A sua classe principal, a classe de tarefa, deve ser a seguinte:

![Diagrama da classe Tarefa](diagrama.png)

Não se esqueça de gerar a sua migration para atualização no banco de dados.

## Métodos esperados
É esperado que você crie os seus métodos conforme a seguir:


**Swagger**


![Métodos Swagger](18.png)


**Endpoints**


| Verbo  | Endpoint                | Parâmetro | Body          |
|--------|-------------------------|-----------|---------------|
| GET    | /Tarefa/{id}            | id        | N/A           |
| PUT    | /Tarefa/{id}            | id        | Schema Tarefa |
| DELETE | /Tarefa/{id}            | id        | N/A           |
| GET    | /Tarefa/ObterTodos      | N/A       | N/A           |
| GET    | /Tarefa/ObterPorTitulo  | titulo    | N/A           |
| GET    | /Tarefa/ObterPorData    | data      | N/A           |
| GET    | /Tarefa/ObterPorStatus  | status    | N/A           |
| POST   | /Tarefa                 | N/A       | Schema Tarefa |

Esse é o schema (model) de Tarefa, utilizado para passar para os métodos que exigirem

```json
{
  "id": 0,
  "titulo": "string",
  "descricao": "string",
  "data": "2022-06-08T01:31:07.056Z",
  "status": "Pendente"
}
```


## Explicações:


**ObterPorId (GET /Tarefa/{id}):**
![ObterPorId](15.png)

![ObterPorId](16.png)

Busca a tarefa pelo ID. Se não for encontrada, retorna NotFound(). Caso contrário, retorna a tarefa com Ok(tarefa).

**ObterTodos (GET /Tarefa/ObterTodos):**

![ObterTodos](3.png)

Retorna todas as tarefas presentes no banco de dados com Ok(tarefas).

**ObterPorTitulo (GET /Tarefa/ObterPorTitulo):**

![ObterPorTitulo](4.png)

![ObterPorTitulo](5.png)

![ObterPorTitulo](6.png)

![ObterPorTitulo](7.png)

Busca as tarefas que contêm o título fornecido. Usa Contains para a pesquisa e retorna a lista com Ok(tarefas).

**ObterPorData (GET /Tarefa/ObterPorData):**

![ObterPorData](8.png)

![ObterPorData](9.png)

![ObterPorData](10.png)

Filtra as tarefas pela data específica e retorna a lista.

**ObterPorStatus (GET /Tarefa/ObterPorStatus):**

![ObterPorStatus](11.png)

![ObterPorStatus](12.png)

Filtra as tarefas pelo status fornecido e retorna a lista.

**Criar (POST /Tarefa):**

![Criar](1.png)

![Criar](2.png)

Adiciona uma nova tarefa ao banco de dados. Se a data for inválida, retorna um erro. Caso contrário, adiciona a tarefa e salva as mudanças, retornando a tarefa criada com CreatedAtAction.

**Atualizar (PUT /Tarefa/{id}):**

![Atualizar](13.png)

![Atualizar](14.png)

Atualiza uma tarefa existente. Verifica se a tarefa existe e se a data é válida. Atualiza as propriedades da tarefa e salva as mudanças.

**Deletar (DELETE /Tarefa/{id}):**

![Deletar](17.png)

Remove uma tarefa pelo ID. Se não for encontrada, retorna NotFound(). Caso contrário, remove a tarefa e salva as mudanças, retornando NoContent().


## Solução
O código está pela metade, e você deverá dar continuidade obedecendo as regras descritas acima, para que no final, tenhamos um programa funcional. Procure pela palavra comentada "TODO" no código, em seguida, implemente conforme as regras acima.