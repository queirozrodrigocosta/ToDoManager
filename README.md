# ToDoManager

exercicio de Node.js com Express e JWT

aluno: Rodrigo Alberto Queiroz Costa
matricula: 1931088038

Avaliação
4.1 Requisição 1 (1 ponto)
Simples requisição para a raiz do sistema. Ela não deve ser barrada pelo filtro de segurança.
4.1.1 Requisição
GET /
4.1.2 Resposta esperada
Corpo:
{'message':'ok'}
4.2 Requisição 2 (1 ponto)
Requisição passando dados incorretos para o login. Repare no código de resposta e mensagem
4.2.1 Requisição
POST /login
Header:
{ 'Content-Type': 'application/json' }
Corpo:
{
'username': 'usuario',
'password': 'senhaErrada'
}
107
108 CAPÍTULO 4. AVALIAÇÃO
4.2.2 Resposta esperada
Status: 401 Corpo (JSON)
{ message: 'Error in username or password' }
4.3 Requisição 3 (1 ponto)
Requisição para realizar o login. O esperado é que a requisição seja feita com sucesso e o token devolvido
por essa requisição será usado nas próximas requisições.
4.3.1 Requisição
POST /login
Header:
{ 'Content-Type': 'application/json' }
Corpo:
{
'username': 'usuario',
'password': '123456'
}
4.3.2 Resposta esperada
Status: 200 Corpo (JSON)
{'token':'<algum token valido>'}
4.4 Requisição 4 (1 ponto)
Requisição adicionando uma nova tarefa no sistema. O id será usado para referência.
4.4.1 Requisição
POST /tasks
Header:
{ 'Content-Type': 'application/json' }
Corpo:
{
'title': 'Lavar louça',
'description': 'Lavar louça acumulada de 3 dias',
'isDone':false,
'isPriority':false
}
4.5. REQUISIÇÃO 5 (1 PONTO) 109
4.4.2 Resposta esperada
Status: 201 Corpo (JSON)
{ title: 'Lavar louça',
description: 'Lavar louça acumulada de 3 dias',
isDone: false,
isPriority: false,
id: '<id da tarefa>' }
4.5 Requisição 5 (1 ponto)
Requisição adicionando uma outra tarefa no sistema.
4.5.1 Requisição
POST /tasks
Header:
{ 'Content-Type': 'application/json' }
Corpo:
{
'title': 'Levar cachorro para passear',
'description': 'O cachorro esta doido para passear',
'isDone':false,
'isPriority':false
}
4.5.2 Resposta esperada
Status: 201 Corpo (JSON)
{ 'title': 'Levar cachorro para passear',
'description': 'O cachorro esta doido para passear',
isDone: false,
isPriority: false,
id: '<id da tarefa>' }
4.6 Requisição 6 (1 ponto)
Requisição listando as tarefas. Deve contar a tarefa adicionada na questão 4 e na questão 6 (pode conter
outras tarefas, não tem problema).
4.6.1 Requisição
GET /tasks
110 CAPÍTULO 4. AVALIAÇÃO
4.6.2 Resposta esperada
Status: 200 Corpo (JSON)
[{ title: 'Lavar louça',
description: 'Lavar louça acumulada de 3 dias',
isDone: false,
isPriority: false,
id: '<id da tarefa>' },
{ 'title': 'Levar cachorro para passear',
'description': 'O cachorro esta doido para passear',
isDone: false,
isPriority: false,
id: '<id da tarefa>' }]
4.7 Requisição 7 (1 ponto)
Requisição para alterar a tarefa gravada na questão 4, o atributo isDone será alterado para true.
4.7.1 Requisição
PUT /tasks/:idDaQuestao04
Header:
{ 'Content-Type': 'application/json' }
Corpo:
{
'title': 'Lavar louça',
'description': 'Lavar louça acumulada de 3 dias',
'isDone':true,
'isPriority':false
}
4.7.2 Resposta esperada
Status: 200 Corpo (JSON)
{ title: 'Lavar louça',
description: 'Lavar louça acumulada de 3 dias',
isDone: true,
isPriority: false,
id: '<id da tarefa>' }
4.8 Requisição 8 (1 ponto)
Buscando a tarefa gravada na questão 4, depois de alterada.
4.9. REQUISIÇÃO 9 (1 PONTO) 111
4.8.1 Requisição
GET /tasks/:idDaQuestao04
4.8.2 Resposta esperada
Status: 200 Corpo (JSON)
{ title: 'Lavar louça',
description: 'Lavar louça acumulada de 3 dias',
isDone: true,
isPriority: false,
id: '<id da tarefa>' }
4.9 Requisição 9 (1 ponto)
Apagando tarefa gravada na questão 4
4.9.1 Requisição
DELETE /tasks/:idDaQuestao04
4.9.2 Resposta esperada
Status: 200 Corpo (JSON)
{ title: 'Lavar louça',
description: 'Lavar louça acumulada de 3 dias',
isDone: true,
isPriority: false,
id: '<id da tarefa>' }
4.10 Requisição 6 (1 ponto)
Requisição listando as tarefas. Não deve contar a tarefa adicionada na questão 4 e deve conter a tarefa da
questão 6 (pode conter outras tarefas, não tem problema).
4.10.1 Requisição
GET /tasks
112 CAPÍTULO 4. AVALIAÇÃO
4.10.2 Resposta esperada
Status: 200 Corpo (JSON)
[{ 'title': 'Levar cachorro para passear',
'description': 'O cachorro esta doido para passear',
isDone: false,
isPriority: false,
id: '<id da tarefa>' }]
